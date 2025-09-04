// DOM Elements
const navbar = document.getElementById('navbar');
const navToggle = document.getElementById('nav-toggle');
const navMenu = document.getElementById('nav-menu');
const navLinks = document.querySelectorAll('.nav-link');

// Mobile Navigation Toggle
navToggle.addEventListener('click', () => {
    navMenu.classList.toggle('active');
    navToggle.classList.toggle('active');
});

// Close mobile menu when clicking on a link
navLinks.forEach(link => {
    link.addEventListener('click', () => {
        navMenu.classList.remove('active');
        navToggle.classList.remove('active');
    });
});

// Navbar scroll effect
window.addEventListener('scroll', () => {
    if (window.scrollY > 100) {
        navbar.classList.add('scrolled');
    } else {
        navbar.classList.remove('scrolled');
    }
});

// Smooth scrolling for navigation links
navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        const targetId = link.getAttribute('href');
        const targetSection = document.querySelector(targetId);
        
        if (targetSection) {
            const offsetTop = targetSection.offsetTop - 70; // Account for navbar height
            window.scrollTo({
                top: offsetTop,
                behavior: 'smooth'
            });
        }
    });
});

// Active navigation link highlighting
function updateActiveNavLink() {
    const sections = document.querySelectorAll('section[id]');
    const scrollPos = window.scrollY + 100;

    sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.offsetHeight;
        const sectionId = section.getAttribute('id');
        const navLink = document.querySelector(`.nav-link[href="#${sectionId}"]`);

        if (scrollPos >= sectionTop && scrollPos < sectionTop + sectionHeight) {
            navLinks.forEach(link => link.classList.remove('active'));
            if (navLink) {
                navLink.classList.add('active');
            }
        }
    });
}

window.addEventListener('scroll', updateActiveNavLink);

// Intersection Observer for animations
const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
};

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('animate-in');
        }
    });
}, observerOptions);

// Observe all animated elements
document.addEventListener('DOMContentLoaded', () => {
    const animatedElements = document.querySelectorAll(`
        .hero-content,
        .hero-visual,
        .section-header,
        .content-text,
        .comparison-card,
        .pillar-card,
        .objective-card,
        .function-item,
        .example-card,
        .timeline-item,
        .closing-content
    `);

    animatedElements.forEach(el => {
        el.classList.add('animate-element');
        observer.observe(el);
    });
});

// Parallax effect for hero section
window.addEventListener('scroll', () => {
    const scrolled = window.pageYOffset;
    const hero = document.querySelector('.hero');
    const heroContent = document.querySelector('.hero-content');
    const heroVisual = document.querySelector('.hero-visual');
    
    if (hero && scrolled < hero.offsetHeight) {
        const rate = scrolled * -0.5;
        if (heroContent) {
            heroContent.style.transform = `translateY(${rate}px)`;
        }
        if (heroVisual) {
            heroVisual.style.transform = `translateY(${rate * 0.8}px)`;
        }
    }
});

// Counter animation for statistics (if needed in future)
function animateCounter(element, target, duration = 2000) {
    let start = 0;
    const increment = target / (duration / 16);
    
    const timer = setInterval(() => {
        start += increment;
        element.textContent = Math.floor(start);
        
        if (start >= target) {
            element.textContent = target;
            clearInterval(timer);
        }
    }, 16);
}

// Typing effect for hero title
function typeWriter(element, text, speed = 100) {
    let i = 0;
    element.innerHTML = '';
    
    function type() {
        if (i < text.length) {
            element.innerHTML += text.charAt(i);
            i++;
            setTimeout(type, speed);
        }
    }
    
    type();
}

// Initialize typing effect on load (optional - can be enabled)
// document.addEventListener('DOMContentLoaded', () => {
//     const heroTitle = document.querySelector('.hero-title');
//     if (heroTitle) {
//         const originalText = heroTitle.textContent;
//         typeWriter(heroTitle, originalText, 50);
//     }
// });

// Card hover effects
document.addEventListener('DOMContentLoaded', () => {
    const cards = document.querySelectorAll(`
        .comparison-card,
        .pillar-card,
        .objective-card,
        .example-card,
        .function-item
    `);

    cards.forEach(card => {
        card.addEventListener('mouseenter', function() {
            this.style.transform = 'translateY(-10px) scale(1.02)';
        });

        card.addEventListener('mouseleave', function() {
            this.style.transform = 'translateY(0) scale(1)';
        });
    });
});

// Scroll to top functionality
function createScrollToTopButton() {
    const button = document.createElement('button');
    button.innerHTML = '<i class="fas fa-chevron-up"></i>';
    button.className = 'scroll-to-top';
    button.style.cssText = `
        position: fixed;
        bottom: 30px;
        right: 30px;
        width: 50px;
        height: 50px;
        background: linear-gradient(135deg, #4CAF50, #45a049);
        color: white;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        opacity: 0;
        visibility: hidden;
        transition: all 0.3s ease;
        z-index: 1000;
        box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
    `;

    button.addEventListener('click', () => {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    });

    button.addEventListener('mouseenter', () => {
        button.style.transform = 'translateY(-3px)';
        button.style.boxShadow = '0 10px 25px rgba(76, 175, 80, 0.4)';
    });

    button.addEventListener('mouseleave', () => {
        button.style.transform = 'translateY(0)';
        button.style.boxShadow = '0 5px 15px rgba(76, 175, 80, 0.3)';
    });

    document.body.appendChild(button);

    window.addEventListener('scroll', () => {
        if (window.scrollY > 500) {
            button.style.opacity = '1';
            button.style.visibility = 'visible';
        } else {
            button.style.opacity = '0';
            button.style.visibility = 'hidden';
        }
    });
}

// Initialize scroll to top button
document.addEventListener('DOMContentLoaded', createScrollToTopButton);

// Form validation (if forms are added later)
function validateForm(form) {
    const inputs = form.querySelectorAll('input[required], textarea[required]');
    let isValid = true;

    inputs.forEach(input => {
        if (!input.value.trim()) {
            input.classList.add('error');
            isValid = false;
        } else {
            input.classList.remove('error');
        }
    });

    return isValid;
}

// Loading animation
function showLoading() {
    const loader = document.createElement('div');
    loader.className = 'loader';
    loader.innerHTML = `
        <div class="loader-spinner">
            <i class="fas fa-campground"></i>
        </div>
    `;
    loader.style.cssText = `
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(255, 255, 255, 0.9);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 9999;
        opacity: 1;
        transition: opacity 0.5s ease;
    `;

    const spinner = loader.querySelector('.loader-spinner');
    spinner.style.cssText = `
        font-size: 3rem;
        color: #4CAF50;
        animation: spin 1s linear infinite;
    `;

    // Add spin animation
    const style = document.createElement('style');
    style.textContent = `
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    `;
    document.head.appendChild(style);

    document.body.appendChild(loader);

    // Remove loader after page load
    window.addEventListener('load', () => {
        setTimeout(() => {
            loader.style.opacity = '0';
            setTimeout(() => {
                if (loader.parentNode) {
                    loader.parentNode.removeChild(loader);
                }
            }, 500);
        }, 500);
    });
}

// Initialize loading animation
if (document.readyState === 'loading') {
    showLoading();
}

// Add CSS animations for elements
const animationStyles = document.createElement('style');
animationStyles.textContent = `
    .animate-element {
        opacity: 0;
        transform: translateY(30px);
        transition: all 0.6s ease;
    }

    .animate-element.animate-in {
        opacity: 1;
        transform: translateY(0);
    }

    .nav-link.active {
        color: #2563eb;
    }

    .nav-link.active::after {
        width: 100%;
    }

    .scroll-to-top:hover {
        transform: translateY(-3px) scale(1.1);
    }

    /* Stagger animation for grid items */
    .pillars-grid .pillar-card,
    .objectives-grid .objective-card,
    .examples-grid .example-card {
        transition-delay: calc(var(--index, 0) * 0.1s);
    }

    /* Timeline animation */
    .timeline-item {
        transition-delay: calc(var(--index, 0) * 0.2s);
    }

    /* Hover effects */
    .comparison-card,
    .pillar-card,
    .objective-card,
    .example-card,
    .function-item {
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    /* Button hover effects */
    .btn-primary,
    .btn-secondary {
        position: relative;
        overflow: hidden;
    }

    .btn-primary::before,
    .btn-secondary::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
        transition: left 0.5s;
    }

    .btn-primary:hover::before,
    .btn-secondary:hover::before {
        left: 100%;
    }
`;

document.head.appendChild(animationStyles);

// Add index data attributes for staggered animations
document.addEventListener('DOMContentLoaded', () => {
    const gridItems = document.querySelectorAll(`
        .pillars-grid .pillar-card,
        .objectives-grid .objective-card,
        .examples-grid .example-card,
        .timeline-item
    `);

    gridItems.forEach((item, index) => {
        item.style.setProperty('--index', index);
    });
});

// Lazy loading for images (if images are added later)
function lazyLoadImages() {
    const images = document.querySelectorAll('img[data-src]');
    
    const imageObserver = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const img = entry.target;
                img.src = img.dataset.src;
                img.classList.remove('lazy');
                observer.unobserve(img);
            }
        });
    });

    images.forEach(img => imageObserver.observe(img));
}

// Initialize lazy loading
document.addEventListener('DOMContentLoaded', lazyLoadImages);

// Performance optimization: Throttle scroll events
function throttle(func, wait) {
    let timeout;
    return function executedFunction(...args) {
        const later = () => {
            clearTimeout(timeout);
            func(...args);
        };
        clearTimeout(timeout);
        timeout = setTimeout(later, wait);
    };
}

// Apply throttling to scroll events
const throttledScrollHandler = throttle(() => {
    updateActiveNavLink();
}, 100);

window.addEventListener('scroll', throttledScrollHandler);

// Console welcome message
console.log(`
🏕️ Infraestructura Scout - One Page Website
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✨ Website successfully loaded!
🛠️ Built with modern web technologies
🎯 Focused on user experience and accessibility

For technical support or questions, please contact the development team.
`);

// Error handling for missing elements
function handleMissingElements() {
    const requiredElements = [
        { selector: '#navbar', name: 'Navigation bar' },
        { selector: '#nav-toggle', name: 'Navigation toggle' },
        { selector: '#nav-menu', name: 'Navigation menu' },
        { selector: '.hero', name: 'Hero section' }
    ];

    requiredElements.forEach(element => {
        if (!document.querySelector(element.selector)) {
            console.warn(`⚠️ Missing element: ${element.name} (${element.selector})`);
        }
    });
}

// Initialize error handling
document.addEventListener('DOMContentLoaded', handleMissingElements);
