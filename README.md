// Chud University site behavior.
// The application form now POSTs to /api/apply (a Cloudflare Pages Function)
// instead of calling Discord directly — the webhook secret lives server-side.

function initScrollReveal() {
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.15, rootMargin: '0px 0px -60px 0px' });
    reveals.forEach(el => observer.observe(el));
}

// --- Modal handling with focus management -------------------------------

let lastFocused = null;

function openModal(modal) {
    lastFocused = document.activeElement;
    modal.classList.remove('hidden');
    modal.classList.add('flex');
    document.body.style.overflow = 'hidden';
    const focusable = modal.querySelector('input, select, textarea, button');
    if (focusable) focusable.focus();
}

function closeModal(modal) {
    modal.classList.remove('flex');
    modal.classList.add('hidden');
    document.body.style.overflow = '';
    if (lastFocused && typeof lastFocused.focus === 'function') lastFocused.focus();
}

// Keep Tab inside an open modal — prevents keyboard users from tabbing into
// the page behind it.
function trapFocus(e) {
    if (e.key !== 'Tab') return;
    const modal = document.querySelector('#application-modal.flex, #program-modal.flex');
    if (!modal) return;
    const items = modal.querySelectorAll(
        'a[href], button:not([disabled]), input:not([disabled]), select:not([disabled]), textarea:not([disabled])'
    );
    if (!items.length) return;
    const first = items[0];
    const last = items[items.length - 1];
    if (e.shiftKey && document.activeElement === first) {
        e.preventDefault();
        last.focus();
    } else if (!e.shiftKey && document.activeElement === last) {
        e.preventDefault();
        first.focus();
    }
}

function showApplicationModal() { openModal(document.getElementById('application-modal')); }
function hideApplicationModal() { closeModal(document.getElementById('application-modal')); }

let currentProgram = null;

const PROGRAMS = {
    gooning: {
        title: 'Gooning Studies',
        degree: 'Bachelor of Gooning (B.G.) • Master of Gooning (M.G.)',
        icon: 'fa-infinity',
        color: '#0F766E',
        desc: 'Our flagship program combines rigorous practical training with deep theoretical inquiry into the philosophy, physiology, and cultural significance of gooning.',
        details: [
            'Core curriculum includes endurance optimization, philosophical frameworks, community leadership, and archival research methodology.',
            'Students complete a capstone "Great Goon" project under faculty mentorship.',
            'Graduates consistently achieve top placement in leading online communities and research collectives.'
        ],
        stats: '1,142 current majors • 94% placement rate'
    },
    psychology: {
        title: 'Psychology',
        degree: 'Bachelor of Arts (B.A.) • Doctor of Philosophy (Ph.D.)',
        icon: 'fa-brain',
        color: '#4338CA',
        desc: 'A specialized curriculum examining the contemporary male experience, online identity formation, and the psychological dimensions of digital subcultures.',
        details: [
            'Focus areas include incel phenomenology, parasocial attachment theory, and digital identity construction.',
            'Students conduct original research using both qualitative and quantitative methods.',
            'Faculty includes leading researchers in online subculture psychology.'
        ],
        stats: '687 current majors • Strong research output'
    },
    discord: {
        title: 'Discord Moderation',
        degree: 'Certificate • Bachelor of Science (B.S.)',
        icon: 'fa-shield-halved',
        color: '#0E7490',
        desc: 'Professional training in rule adjudication, de-escalation techniques, meme governance, and the cultivation of high-signal digital spaces.',
        details: [
            'Hands-on labs in active server environments with real-time moderation scenarios.',
            'Curriculum covers conflict resolution, content policy development, and community health metrics.',
            'Graduates are actively recruited by the most demanding servers in the ecosystem.'
        ],
        stats: '1,018 current students • 68 servers currently moderated by alumni'
    }
};

// Build text content as DOM nodes rather than innerHTML so program data can
// never be interpreted as markup. (Static here, but cheap insurance.)
function showProgramModal(program) {
    const modal = document.getElementById('program-modal');
    const header = document.getElementById('program-modal-header');
    const body = document.getElementById('program-modal-body');
    const content = PROGRAMS[program];
    if (!content) return;
    currentProgram = program;

    header.innerHTML = '';
    const headWrap = document.createElement('div');
    headWrap.className = 'flex items-center gap-x-4';
    headWrap.innerHTML = `
        <div class="w-12 h-12 rounded-2xl flex items-center justify-center" style="background-color: ${content.color}20; color: ${content.color}">
            <i class="fa-solid ${content.icon} text-3xl"></i>
        </div>
        <div>
            <div class="font-bold text-3xl tracking-[-0.6px]"></div>
            <div class="text-sm text-slate-500 mt-0.5"></div>
        </div>`;
    headWrap.querySelector('.font-bold').textContent = content.title;
    headWrap.querySelector('.text-slate-500').textContent = content.degree;
    header.appendChild(headWrap);

    body.innerHTML = '';
    const desc = document.createElement('p');
    desc.className = 'text-[15.2px] text-slate-600 leading-relaxed';
    desc.textContent = content.desc;
    body.appendChild(desc);

    const section = document.createElement('div');
    section.className = 'mt-7';
    section.innerHTML = '<div class="uppercase text-xs tracking-[2px] text-slate-500 font-bold mb-3">PROGRAM HIGHLIGHTS</div>';
    const ul = document.createElement('ul');
    ul.className = 'space-y-2.5 text-[14.8px] text-slate-600';
    content.details.forEach(d => {
        const li = document.createElement('li');
        li.className = 'flex gap-x-3';
        const dot = document.createElement('span');
        dot.className = 'mt-1.5 block w-1.5 h-1.5 rounded-full flex-shrink-0';
        dot.style.backgroundColor = content.color;
        li.appendChild(dot);
        li.appendChild(document.createTextNode(' ' + d));
        ul.appendChild(li);
    });
    section.appendChild(ul);
    body.appendChild(section);

    const stats = document.createElement('div');
    stats.className = 'mt-8 pt-6 border-t text-sm text-slate-500 font-medium';
    stats.textContent = content.stats;
    body.appendChild(stats);

    openModal(modal);
}

function hideProgramModal() { closeModal(document.getElementById('program-modal')); }

function toggleMobileMenu() {
    const menu = document.getElementById('mobile-menu');
    const icon = document.getElementById('mobile-menu-icon');
    const open = menu.classList.toggle('hidden');
    icon.classList.toggle('fa-bars', open);
    icon.classList.toggle('fa-times', !open);
}

// --- Form submission ----------------------------------------------------

function clearFieldErrors(form) {
    form.querySelectorAll('.field-error').forEach(el => el.classList.remove('field-error'));
    form.querySelectorAll('.error-text').forEach(el => el.remove());
}

function markError(input, message) {
    input.classList.add('field-error');
    const note = document.createElement('div');
    note.className = 'error-text';
    note.textContent = message;
    input.parentElement.appendChild(note);
}

function validate(form) {
    clearFieldErrors(form);
    let ok = true;
    const name = form.full_name;
    const email = form.email;
    const program = form.intended_program;
    const cert = form.certification_type;
    const statement = form.personal_statement;

    if (!name.value.trim()) { markError(name, 'Enter your full name.'); ok = false; }
    if (!/^[^@\s]+@[^@\s]+\.[^@\s]+$/.test(email.value.trim())) { markError(email, 'Enter a valid email address.'); ok = false; }
    if (!program.value) { markError(program, 'Choose a program.'); ok = false; }
    if (!cert.value) { markError(cert, 'Choose a certification type.'); ok = false; }
    if (!statement.value.trim()) { markError(statement, 'Write a personal statement.'); ok = false; }
    return ok;
}

async function submitApplication(e) {
    e.preventDefault();
    const form = document.getElementById('application-form');
    if (!validate(form)) return;

    const submitBtn = form.querySelector('button[type="submit"]');
    const original = submitBtn.textContent;
    submitBtn.disabled = true;
    submitBtn.textContent = 'Submitting…';

    const payload = {
        full_name: form.full_name.value,
        email: form.email.value,
        intended_program: form.intended_program.value,
        certification_type: form.certification_type.value,
        personal_statement: form.personal_statement.value,
        company: form.company ? form.company.value : '' // honeypot
    };

    try {
        const res = await fetch('/api/apply', {
            method: 'POST',
            headers: { 'content-type': 'application/json' },
            body: JSON.stringify(payload)
        });
        const data = await res.json().catch(() => ({}));
        if (!res.ok || !data.ok) {
            throw new Error(data.error || 'Submission failed. Please try again.');
        }
        renderSuccess(form.parentElement);
    } catch (err) {
        submitBtn.disabled = false;
        submitBtn.textContent = original;
        let banner = form.querySelector('.submit-error');
        if (!banner) {
            banner = document.createElement('p');
            banner.className = 'submit-error error-text text-center';
            form.insertBefore(banner, submitBtn.parentElement);
        }
        banner.textContent = err.message;
    }
}

function renderSuccess(container) {
    container.innerHTML = `
        <div class="p-11 text-center">
            <div class="mx-auto w-16 h-16 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center mb-7">
                <i class="fa-solid fa-check text-[29px]"></i>
            </div>
            <h3 class="text-[26px] font-semibold tracking-[-0.4px] mb-3">Application received</h3>
            <p class="text-slate-600 max-w-[26ch] mx-auto">Your submission has been forwarded to the Board of Certified Chuds for review.</p>
            <div class="mt-8 text-sm text-slate-500 leading-relaxed">
                You'll receive a decision via email within 6–8 weeks.<br>
                In the meantime, review our <span class="font-medium">Gooning 101</span> preparatory materials.
            </div>
            <button onclick="hideApplicationModal()"
                    class="mt-9 px-9 py-2.5 text-sm font-semibold border border-slate-300 hover:bg-slate-50 active:bg-slate-100 rounded-2xl transition-colors">
                Return to homepage
            </button>
        </div>`;
}

function animateStats() {
    const prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
    document.querySelectorAll('.stat-number').forEach(stat => {
        const originalText = stat.textContent.trim();
        const target = parseInt(originalText.replace(/[^0-9]/g, ''), 10);
        if (!target || target === 1 || prefersReduced) return;

        const duration = 1350;
        const startTime = performance.now();
        function update(currentTime) {
            const progress = Math.min((currentTime - startTime) / duration, 1);
            const eased = 1 - Math.pow(1 - progress, 3);
            const current = Math.floor(target * eased);
            if (originalText.includes('%')) stat.textContent = current + '%';
            else if (originalText.includes(',')) stat.textContent = current.toLocaleString();
            else stat.textContent = current;
            if (progress < 1) requestAnimationFrame(update);
            else stat.textContent = originalText;
        }
        requestAnimationFrame(update);
    });
}

document.addEventListener('keydown', function (e) {
    if (e.key === 'Escape') {
        const appModal = document.getElementById('application-modal');
        const progModal = document.getElementById('program-modal');
        if (!appModal.classList.contains('hidden')) hideApplicationModal();
        else if (!progModal.classList.contains('hidden')) hideProgramModal();
    }
    trapFocus(e);
});

function init() {
    initScrollReveal();

    const statsSection = document.querySelector('[data-stats]');
    if (statsSection) {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    setTimeout(animateStats, 220);
                    observer.disconnect();
                }
            });
        }, { threshold: 0.5 });
        observer.observe(statsSection);
    }

    const navLinks = document.querySelectorAll('nav a[href^="#"]');
    const sections = ['about', 'academics', 'campuses', 'admissions'].map(id => document.getElementById(id));
    window.addEventListener('scroll', () => {
        let current = '';
        sections.forEach(section => {
            if (section && window.scrollY >= section.offsetTop - 180) current = section.id;
        });
        navLinks.forEach(link => {
            link.classList.toggle('nav-active', link.getAttribute('href') === `#${current}`);
        });
    });
}

init();
