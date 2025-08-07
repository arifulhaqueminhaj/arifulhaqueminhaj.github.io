<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ariful Haque Minhaj - Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .gradient-bg { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .card-hover { transition: all 0.3s ease; }
        .card-hover:hover { transform: translateY(-5px); box-shadow: 0 20px 40px rgba(0,0,0,0.1); }
        .skill-bar { transition: width 1s ease-in-out; }
        .animate-fade-in { animation: fadeIn 0.6s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .name-glow { animation: nameGlow 1s ease-in-out; }
        @keyframes nameGlow { 
            0% { text-shadow: 0 0 5px rgba(255,255,255,0.8); transform: scale(1); }
            50% { text-shadow: 0 0 20px rgba(255,255,255,1), 0 0 30px rgba(102,126,234,0.8); transform: scale(1.05); }
            100% { text-shadow: 0 0 5px rgba(255,255,255,0.8); transform: scale(1); }
        }
        .profile-pic { 
            width: 128px; 
            height: 128px; 
            object-fit: cover; 
            border: 4px solid rgba(255,255,255,0.3);
            transition: all 0.3s ease;
        }
        .profile-pic:hover { border-color: rgba(255,255,255,0.6); }
        .upload-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
            cursor: pointer;
        }
        .profile-container:hover .upload-overlay { opacity: 1; }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Navigation -->
    <nav class="fixed top-0 w-full bg-white/90 backdrop-blur-sm shadow-sm z-50">
        <div class="max-w-6xl mx-auto px-4 py-4">
            <div class="flex justify-between items-center">
                <h1 class="text-2xl font-bold text-gray-800 cursor-pointer transition-all duration-300" id="nav-name" onclick="glowName()">Ariful Haque Minhaj</h1>
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="text-gray-600 hover:text-blue-600 transition-colors">Home</a>
                    <a href="#about" class="text-gray-600 hover:text-blue-600 transition-colors">About</a>
                    <a href="#education" class="text-gray-600 hover:text-blue-600 transition-colors">Education</a>
                    <a href="#skills" class="text-gray-600 hover:text-blue-600 transition-colors">Skills</a>
                    <a href="#projects" class="text-gray-600 hover:text-blue-600 transition-colors">Projects</a>
                    <a href="#contact" class="text-gray-600 hover:text-blue-600 transition-colors">Contact</a>
                </div>
                <button id="mobile-menu-btn" class="md:hidden">
                    <i class="fas fa-bars text-gray-600"></i>
                </button>
            </div>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobile-menu" class="fixed top-0 left-0 w-full h-full bg-white z-40 transform -translate-x-full transition-transform duration-300 md:hidden">
        <div class="p-6">
            <button id="close-menu" class="float-right text-2xl">&times;</button>
            <div class="mt-12 space-y-6">
                <a href="#home" class="block text-xl text-gray-600 hover:text-blue-600">Home</a>
                <a href="#about" class="block text-xl text-gray-600 hover:text-blue-600">About</a>
                <a href="#education" class="block text-xl text-gray-600 hover:text-blue-600">Education</a>
                <a href="#skills" class="block text-xl text-gray-600 hover:text-blue-600">Skills</a>
                <a href="#projects" class="block text-xl text-gray-600 hover:text-blue-600">Projects</a>
                <a href="#contact" class="block text-xl text-gray-600 hover:text-blue-600">Contact</a>
            </div>
        </div>
    </div>

    <!-- Hero Section -->
    <section id="home" class="gradient-bg min-h-screen flex items-center justify-center text-white">
        <div class="text-center animate-fade-in">
            <div class="w-32 h-32 mx-auto mb-6 relative profile-container">
                <img id="profile-image" src="" alt="Profile" class="w-32 h-32 bg-white/20 rounded-full profile-pic hidden">
                <div id="default-avatar" class="w-32 h-32 bg-white/20 rounded-full flex items-center justify-center">
                    <i class="fas fa-user text-4xl"></i>
                </div>
                <div class="upload-overlay rounded-full" onclick="document.getElementById('profile-upload').click()">
                    <i class="fas fa-camera text-white text-2xl"></i>
                </div>
                <input type="file" id="profile-upload" accept="image/*" style="display: none;">
            </div>
            <h1 class="text-5xl md:text-6xl font-bold mb-4 cursor-pointer transition-all duration-300" id="hero-name" onclick="glowName()">Ariful Haque Minhaj</h1>
            <p class="text-xl md:text-2xl mb-6 opacity-90">Computer Science & Engineering Student</p>
            <p class="text-lg mb-8 max-w-2xl mx-auto opacity-80">Experienced professional with expertise in Python and data analysis, driving meaningful outcomes through technical innovation and strategic collaboration.</p>
            <div class="space-x-4">
                <a href="#contact" class="bg-white text-blue-600 px-8 py-3 rounded-full font-semibold hover:bg-gray-100 transition-colors">Get In Touch</a>
                <a href="#projects" class="border-2 border-white px-8 py-3 rounded-full font-semibold hover:bg-white hover:text-blue-600 transition-colors">View Projects</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-white">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-16 text-gray-800">About Me</h2>
            <div class="grid md:grid-cols-2 gap-12 items-center">
                <div>
                    <h3 class="text-2xl font-semibold mb-6 text-gray-800">Personal Information</h3>
                    <div class="space-y-4">
                        <div class="flex items-center">
                            <i class="fas fa-calendar-alt text-blue-600 w-6"></i>
                            <span class="ml-3"><strong>Date of Birth:</strong> November 12, 2002</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-flag text-blue-600 w-6"></i>
                            <span class="ml-3"><strong>Nationality:</strong> Bangladeshi</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-heart text-blue-600 w-6"></i>
                            <span class="ml-3"><strong>Marital Status:</strong> Unmarried</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-user text-blue-600 w-6"></i>
                            <span class="ml-3"><strong>Father:</strong> Md. Abul Kashem</span>
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-user text-blue-600 w-6"></i>
                            <span class="ml-3"><strong>Mother:</strong> Sharmin Akhter</span>
                        </div>
                    </div>
                </div>
                <div>
                    <h3 class="text-2xl font-semibold mb-6 text-gray-800">Work Experience</h3>
                    <div class="space-y-6">
                        <div class="border-l-4 border-blue-600 pl-6">
                            <h4 class="text-lg font-semibold text-gray-800">Executive Member</h4>
                            <p class="text-blue-600 font-medium">Youth Skill Development Institute Trust</p>
                            <p class="text-gray-600 mt-2">Led annual budgeting process with precision and strategic insight, driving meaningful outcomes through technical expertise.</p>
                        </div>
                        <div class="border-l-4 border-blue-600 pl-6">
                            <h4 class="text-lg font-semibold text-gray-800">General Member</h4>
                            <p class="text-blue-600 font-medium">IIEC - IUBAT Innovation and Entrepreneurship Center</p>
                            <p class="text-gray-600 mt-2">Contributing to innovation and entrepreneurship initiatives within the university community.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="py-20 bg-gray-50">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-16 text-gray-800">Education</h2>
            <div class="space-y-8">
                <div class="bg-white rounded-lg shadow-lg p-8 card-hover">
                    <div class="flex items-center mb-4">
                        <div class="w-12 h-12 bg-blue-600 rounded-full flex items-center justify-center text-white font-bold">
                            BSc
                        </div>
                        <div class="ml-4">
                            <h3 class="text-xl font-semibold text-gray-800">Bachelor of Science in Computer Science and Engineering</h3>
                            <p class="text-blue-600 font-medium">IUBAT - International University of Business Agriculture and Technology</p>
                        </div>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-gray-600">September 2025 - Present</span>
                        <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full font-semibold">CGPA: 3.97/4.00</span>
                    </div>
                </div>

                <div class="bg-white rounded-lg shadow-lg p-8 card-hover">
                    <div class="flex items-center mb-4">
                        <div class="w-12 h-12 bg-purple-600 rounded-full flex items-center justify-center text-white font-bold">
                            HSC
                        </div>
                        <div class="ml-4">
                            <h3 class="text-xl font-semibold text-gray-800">Higher Secondary Certificate - Science</h3>
                            <p class="text-purple-600 font-medium">Stamford College, Dhaka</p>
                        </div>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-gray-600">2021</span>
                        <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full font-semibold">GPA: 4.29/5.00</span>
                    </div>
                </div>

                <div class="bg-white rounded-lg shadow-lg p-8 card-hover">
                    <div class="flex items-center mb-4">
                        <div class="w-12 h-12 bg-orange-600 rounded-full flex items-center justify-center text-white font-bold">
                            SSC
                        </div>
                        <div class="ml-4">
                            <h3 class="text-xl font-semibold text-gray-800">Secondary School Certificate - Science</h3>
                            <p class="text-orange-600 font-medium">Stamford School, Dhaka</p>
                        </div>
                    </div>
                    <div class="flex justify-between items-center">
                        <span class="text-gray-600">2019</span>
                        <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full font-semibold">GPA: 4.06/5.00</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-20 bg-white">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-16 text-gray-800">Skills & Languages</h2>
            <div class="grid md:grid-cols-2 gap-12">
                <div>
                    <h3 class="text-2xl font-semibold mb-8 text-gray-800">Technical Skills</h3>
                    <div class="space-y-6">
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">Python</span>
                                <span class="text-blue-600">90%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-blue-600 h-3 rounded-full skill-bar" style="width: 90%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">C++</span>
                                <span class="text-blue-600">85%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-blue-600 h-3 rounded-full skill-bar" style="width: 85%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">HTML/CSS</span>
                                <span class="text-blue-600">88%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-blue-600 h-3 rounded-full skill-bar" style="width: 88%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">JavaScript</span>
                                <span class="text-blue-600">80%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-blue-600 h-3 rounded-full skill-bar" style="width: 80%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">Data Analysis</span>
                                <span class="text-blue-600">85%</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-blue-600 h-3 rounded-full skill-bar" style="width: 85%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <div>
                    <h3 class="text-2xl font-semibold mb-8 text-gray-800">Languages</h3>
                    <div class="space-y-6">
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">English</span>
                                <span class="text-green-600">Fluent</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-green-600 h-3 rounded-full skill-bar" style="width: 95%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">French</span>
                                <span class="text-green-600">Fluent</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-green-600 h-3 rounded-full skill-bar" style="width: 90%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">German</span>
                                <span class="text-yellow-600">Basic</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-yellow-600 h-3 rounded-full skill-bar" style="width: 40%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="font-medium text-gray-700">Spanish</span>
                                <span class="text-yellow-600">Basic</span>
                            </div>
                            <div class="w-full bg-gray-200 rounded-full h-3">
                                <div class="bg-yellow-600 h-3 rounded-full skill-bar" style="width: 35%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-20 bg-gray-50">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-16 text-gray-800">Projects</h2>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white rounded-lg shadow-lg overflow-hidden card-hover">
                    <div class="p-8">
                        <div class="flex items-center mb-4">
                            <i class="fas fa-car text-3xl text-blue-600 mr-4"></i>
                            <h3 class="text-xl font-semibold text-gray-800">Car Rental System</h3>
                        </div>
                        <p class="text-gray-600 mb-6">A comprehensive car rental management system built with modern web technologies, featuring user-friendly interface and efficient booking management.</p>
                        <div class="flex items-center justify-between">
                            <div class="flex space-x-2">
                                <span class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm">Web Development</span>
                                <span class="bg-green-100 text-green-800 px-3 py-1 rounded-full text-sm">System Design</span>
                            </div>
                            <a href="https://github.com/arifulhaque12/Car-Rental-System.git" target="_blank" class="text-blue-600 hover:text-blue-800 transition-colors">
                                <i class="fab fa-github text-xl"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-lg shadow-lg overflow-hidden card-hover">
                    <div class="p-8">
                        <div class="flex items-center mb-4">
                            <i class="fas fa-heartbeat text-3xl text-red-600 mr-4"></i>
                            <h3 class="text-xl font-semibold text-gray-800">Healthcare Monitoring System</h3>
                        </div>
                        <p class="text-gray-600 mb-6">Affordable and customer-friendly paralysis patient health care monitoring system based on IoT technology with Arduino integration for real-time health tracking.</p>
                        <div class="flex items-center justify-between">
                            <div class="flex space-x-2">
                                <span class="bg-red-100 text-red-800 px-3 py-1 rounded-full text-sm">IoT</span>
                                <span class="bg-purple-100 text-purple-800 px-3 py-1 rounded-full text-sm">Arduino</span>
                                <span class="bg-orange-100 text-orange-800 px-3 py-1 rounded-full text-sm">Healthcare</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>



    <!-- Contact Section -->
    <section id="contact" class="py-20 gradient-bg text-white">
        <div class="max-w-6xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-16">Get In Touch</h2>
            <div class="grid md:grid-cols-2 gap-12">
                <div>
                    <h3 class="text-2xl font-semibold mb-8">Contact Information</h3>
                    <div class="space-y-6">
                        <div class="flex items-center">
                            <div class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center mr-4">
                                <i class="fas fa-phone text-xl"></i>
                            </div>
                            <div>
                                <p class="font-medium">Phone</p>
                                <p class="opacity-80">01321749193</p>
                            </div>
                        </div>
                        <div class="flex items-center">
                            <div class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center mr-4">
                                <i class="fas fa-envelope text-xl"></i>
                            </div>
                            <div>
                                <p class="font-medium">Email</p>
                                <p class="opacity-80">ariful.minhaj@gmail.com</p>
                            </div>
                        </div>
                        <div class="flex items-center">
                            <div class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center mr-4">
                                <i class="fas fa-map-marker-alt text-xl"></i>
                            </div>
                            <div>
                                <p class="font-medium">Address</p>
                                <p class="opacity-80">Aftabnagar, Dhaka 1209</p>
                            </div>
                        </div>
                    </div>

                    <div class="mt-12">
                        <h4 class="text-xl font-semibold mb-6">Social Links</h4>
                        <div class="flex space-x-4">
                            <a href="https://www.linkedin.com/arifulhaqueminhaj" target="_blank" class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center hover:bg-white/30 transition-colors">
                                <i class="fab fa-linkedin text-xl"></i>
                            </a>
                            <a href="https://github.com/arifulhaqueminhaj" target="_blank" class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center hover:bg-white/30 transition-colors">
                                <i class="fab fa-github text-xl"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <div>
                    <h3 class="text-2xl font-semibold mb-8">Send a Message</h3>
                    <form class="space-y-6" id="contact-form">
                        <div>
                            <input type="text" placeholder="Your Name" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/70 focus:outline-none focus:border-white/50">
                        </div>
                        <div>
                            <input type="email" placeholder="Your Email" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/70 focus:outline-none focus:border-white/50">
                        </div>
                        <div>
                            <textarea rows="5" placeholder="Your Message" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/70 focus:outline-none focus:border-white/50 resize-none"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-white text-blue-600 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors">
                            Send Message
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-8">
        <div class="max-w-6xl mx-auto px-4 text-center">
            <p>&copy; 2024 Ariful Haque Minhaj. All rights reserved.</p>
            <p class="mt-2 opacity-70">Built with passion and dedication</p>
        </div>
    </footer>

    <script>
        // Mobile menu functionality
        const mobileMenuBtn = document.getElementById('mobile-menu-btn');
        const mobileMenu = document.getElementById('mobile-menu');
        const closeMenuBtn = document.getElementById('close-menu');

        mobileMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.remove('-translate-x-full');
        });

        closeMenuBtn.addEventListener('click', () => {
            mobileMenu.classList.add('-translate-x-full');
        });

        // Close mobile menu when clicking on links
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('-translate-x-full');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Contact form functionality
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const name = this.querySelector('input[type="text"]').value;
            const email = this.querySelector('input[type="email"]').value;
            const message = this.querySelector('textarea').value;
            
            if (name && email && message) {
                // Show success message
                alert('Thank you for your message! I will get back to you soon.');
                this.reset();
            } else {
                alert('Please fill in all fields.');
            }
        });

        // Animate skill bars on scroll
        const observerOptions = {
            threshold: 0.5,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const skillBars = entry.target.querySelectorAll('.skill-bar');
                    skillBars.forEach(bar => {
                        bar.style.width = bar.style.width;
                    });
                }
            });
        }, observerOptions);

        const skillsSection = document.getElementById('skills');
        if (skillsSection) {
            observer.observe(skillsSection);
        }

        // Add scroll effect to navigation
        window.addEventListener('scroll', () => {
            const nav = document.querySelector('nav');
            if (window.scrollY > 100) {
                nav.classList.add('bg-white/95');
                nav.classList.remove('bg-white/90');
            } else {
                nav.classList.add('bg-white/90');
                nav.classList.remove('bg-white/95');
            }
        });

        // Profile picture upload functionality
        document.getElementById('profile-upload').addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const profileImage = document.getElementById('profile-image');
                    const defaultAvatar = document.getElementById('default-avatar');
                    
                    profileImage.src = e.target.result;
                    profileImage.classList.remove('hidden');
                    defaultAvatar.classList.add('hidden');
                    
                    // Store in localStorage to persist across page reloads
                    localStorage.setItem('profileImage', e.target.result);
                };
                reader.readAsDataURL(file);
            }
        });

        // Load saved profile picture on page load
        window.addEventListener('load', () => {
            const savedImage = localStorage.getItem('profileImage');
            if (savedImage) {
                const profileImage = document.getElementById('profile-image');
                const defaultAvatar = document.getElementById('default-avatar');
                
                profileImage.src = savedImage;
                profileImage.classList.remove('hidden');
                defaultAvatar.classList.add('hidden');
            }
        });

        // Name glow effect function
        function glowName() {
            const navName = document.getElementById('nav-name');
            const heroName = document.getElementById('hero-name');
            
            // Remove existing animation classes
            navName.classList.remove('name-glow');
            heroName.classList.remove('name-glow');
            
            // Add animation classes
            setTimeout(() => {
                navName.classList.add('name-glow');
                heroName.classList.add('name-glow');
            }, 10);
            
            // Remove animation classes after animation completes
            setTimeout(() => {
                navName.classList.remove('name-glow');
                heroName.classList.remove('name-glow');
            }, 1000);
        }
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96b920fa62837055',t:'MTc1NDU5NDQwMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
