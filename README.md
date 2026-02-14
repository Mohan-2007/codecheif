<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CodeChef Community Portal</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Poppins:wght@600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1E2A38;
            --secondary: #F7931E;
            --background: #FFFFFF;
            --accent: #EAEFF5;
            --text-primary: #1A1A1A;
            --text-secondary: #555555;
            --white: #FFFFFF;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--background);
            color: var(--text-primary);
            line-height: 1.6;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Poppins', sans-serif;
            font-weight: 700;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navbar Styles */
        .navbar {
            position: sticky;
            top: 0;
            background-color: var(--white);
            box-shadow: var(--shadow);
            z-index: 1000;
            padding: 15px 0;
        }

        .navbar-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 20px;
        }

        .logo-text {
            font-family: 'Poppins', sans-serif;
            font-weight: 700;
            font-size: 24px;
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--secondary);
        }

        .auth-buttons {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 10px 20px;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            display: inline-block;
            text-align: center;
        }

        .btn-primary {
            background-color: var(--secondary);
            color: var(--white);
            border: 2px solid var(--secondary);
        }

        .btn-primary:hover {
            background-color: transparent;
            color: var(--secondary);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--primary);
            border: 2px solid var(--primary);
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: var(--white);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, #2a3a48 100%);
            color: var(--white);
            padding: 100px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.25rem;
            margin-bottom: 30px;
            color: var(--accent);
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        /* Section Styles */
        .section {
            padding: 80px 0;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .section-header p {
            color: var(--text-secondary);
            max-width: 600px;
            margin: 0 auto;
        }

        /* Community Introduction */
        .community-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .community-text h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .community-text p {
            margin-bottom: 15px;
            color: var(--text-secondary);
        }

        .community-image {
            background-color: var(--accent);
            height: 300px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--text-secondary);
        }

        /* Vision Section */
        .vision-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .vision-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
        }

        .vision-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        .vision-card h3 {
            color: var(--primary);
            margin-bottom: 15px;
        }

        .vision-card p {
            color: var(--text-secondary);
        }

        /* Events Section */
        .events-filters {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }

        .filter-btn {
            padding: 8px 20px;
            background-color: var(--accent);
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--secondary);
            color: var(--white);
        }

        .events-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .event-card {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .event-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        .event-header {
            background-color: var(--primary);
            color: var(--white);
            padding: 20px;
        }

        .event-header h3 {
            margin-bottom: 10px;
        }

        .event-date {
            color: var(--secondary);
            font-weight: 600;
        }

        .event-body {
            padding: 20px;
        }

        .event-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .status-upcoming {
            background-color: #e8f5e9;
            color: #2e7d32;
        }

        .status-ongoing {
            background-color: #fff3e0;
            color: #f57c00;
        }

        .status-past {
            background-color: #f5f5f5;
            color: #616161;
        }

        /* Projects Section */
        .projects-filters {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .project-card {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        .project-image {
            height: 200px;
            background-color: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
        }

        .project-body {
            padding: 20px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin: 10px 0;
        }

        .tech-tag {
            background-color: var(--accent);
            padding: 4px 10px;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        .project-links {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .project-link {
            color: var(--secondary);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .project-link:hover {
            text-decoration: underline;
        }

        /* Team Section */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .team-member {
            background-color: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
        }

        .team-member:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        .member-image {
            height: 200px;
            background-color: var(--accent);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
        }

        .member-info {
            padding: 20px;
        }

        .member-role {
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 10px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 15px;
        }

        .social-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .social-link:hover {
            color: var(--secondary);
        }

        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }

        .contact-form .form-group {
            margin-bottom: 20px;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
        }

        .contact-form textarea {
            height: 150px;
            resize: vertical;
        }

        .contact-info {
            background-color: var(--accent);
            padding: 30px;
            border-radius: 12px;
        }

        .contact-info h3 {
            margin-bottom: 20px;
            color: var(--primary);
        }

        .map-placeholder {
            height: 200px;
            background-color: var(--white);
            border-radius: 8px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-secondary);
        }

        /* AI Assistant */
        .ai-assistant {
            background: linear-gradient(135deg, var(--primary) 0%, #2a3a48 100%);
            color: var(--white);
            padding: 60px 0;
            text-align: center;
        }

        .ai-assistant h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .ai-assistant p {
            max-width: 700px;
            margin: 0 auto 30px;
            color: var(--accent);
        }

        /* Footer */
        .footer {
            background-color: var(--primary);
            color: var(--white);
            padding: 40px 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .footer-logo {
            font-family: 'Poppins', sans-serif;
            font-weight: 700;
            font-size: 24px;
        }

        .footer-links {
            display: flex;
            gap: 20px;
            list-style: none;
        }

        .footer-links a {
            color: var(--white);
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--secondary);
        }

        /* Scroll to Top */
        .scroll-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background-color: var(--secondary);
            color: var(--white);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 999;
        }

        .scroll-to-top.show {
            opacity: 1;
            visibility: visible;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .navbar-container {
                flex-direction: column;
                gap: 15px;
            }

            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .community-content,
            .contact-container {
                grid-template-columns: 1fr;
            }

            .hero-buttons,
            .footer-content {
                flex-direction: column;
                align-items: center;
            }

            .section {
                padding: 60px 0;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }

            .section-header h2 {
                font-size: 2rem;
            }

            .hero-buttons,
            .events-filters,
            .projects-filters {
                flex-direction: column;
                align-items: center;
            }

            .filter-btn,
            .btn {
                width: 100%;
                max-width: 250px;
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <div class="container navbar-container">
            <a href="#" class="logo">
                <div class="logo-icon">CC</div>
                <div class="logo-text">CodeChef Community</div>
            </a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#events">Events</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#alumni">Alumni</a></li>
                <li><a href="#team">Team</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="auth-buttons">
                <a href="#" class="btn btn-outline">Login</a>
                <a href="#" class="btn btn-primary">Signup</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="container">
            <h1>Building Coders. Shaping Futures.</h1>
            <p>Competitive programming, projects, and career growth</p>
            <div class="hero-buttons">
                <a href="#" class="btn btn-primary">Join Community</a>
                <a href="#events" class="btn btn-outline">Explore Events</a>
            </div>
        </div>
    </section>

    <!-- Community Introduction -->
    <section class="section">
        <div class="container">
            <div class="section-header">
                <h2>About Our Community</h2>
                <p>Who we are and what we stand for</p>
            </div>
            <div class="community-content">
                <div class="community-text">
                    <h3>Who We Are</h3>
                    <p>We are a passionate community of student developers and competitive programmers dedicated to excellence in coding and problem-solving.</p>
                    <p>Our community fosters an environment of discipline, continuous growth, and consistency - the three pillars that define successful programmers.</p>
                    <p>Through regular events, collaborative projects, and mentorship opportunities, we help students develop the skills needed to excel in the tech industry.</p>
                </div>
                <div class="community-image">
                    Community Illustration
                </div>
            </div>
        </div>
    </section>

    <!-- Vision & Purpose -->
    <section class="section" style="background-color: var(--accent);">
        <div class="container">
            <div class="section-header">
                <h2>Our Vision & Purpose</h2>
                <p>Supporting learning, innovation, and future readiness</p>
            </div>
            <div class="vision-cards">
                <div class="vision-card">
                    <h3>Competitive Programming</h3>
                    <p>Regular contests and practice sessions to sharpen algorithmic thinking and problem-solving skills.</p>
                </div>
                <div class="vision-card">
                    <h3>Project Development</h3>
                    <p>Collaborative projects that simulate real-world development environments and build practical experience.</p>
                </div>
                <div class="vision-card">
                    <h3>Career Preparation</h3>
                    <p>Industry-focused training and mentorship to prepare students for technical interviews and professional roles.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- AI Assistant -->
    <section class="ai-assistant">
        <div class="container">
            <h2>Community Guidance AI</h2>
            <p>Our interactive assistant helps you navigate events, explore projects, and understand career paths based on your interests and goals.</p>
            <a href="#" class="btn btn-primary">Get Started</a>
        </div>
    </section>

    <!-- Events Section -->
    <section id="events" class="section">
        <div class="container">
            <div class="section-header">
                <h2>Upcoming Events</h2>
                <p>Join our coding competitions, workshops, and hackathons</p>
            </div>
            <div class="events-filters">
                <button class="filter-btn active">All Events</button>
                <button class="filter-btn">Upcoming</button>
                <button class="filter-btn">Ongoing</button>
                <button class="filter-btn">Past</button>
            </div>
            <div class="events-grid">
                <div class="event-card">
                    <div class="event-header">
                        <h3>Weekly Coding Contest</h3>
                        <div class="event-date">January 25, 2026</div>
                    </div>
                    <div class="event-body">
                        <span class="event-status status-upcoming">Upcoming</span>
                        <p>Test your algorithmic skills in our weekly competitive programming contest featuring problems from CodeChef and Codeforces.</p>
                    </div>
                </div>
                <div class="event-card">
                    <div class="event-header">
                        <h3>Web Development Workshop</h3>
                        <div class="event-date">February 2, 2026</div>
                    </div>
                    <div class="event-body">
                        <span class="event-status status-upcoming">Upcoming</span>
                        <p>Learn modern web development with React, Node.js, and MongoDB in this hands-on workshop series.</p>
                    </div>
                </div>
                <div class="event-card">
                    <div class="event-header">
                        <h3>Annual Hackathon</h3>
                        <div class="event-date">March 15, 2026</div>
                    </div>
                    <div class="event-body">
                        <span class="event-status status-upcoming">Upcoming</span>
                        <p>24-hour coding marathon where teams build innovative solutions to real-world problems.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section" style="background-color: var(--accent);">
        <div class="container">
            <div class="section-header">
                <h2>Featured Projects</h2>
                <p>Innovative solutions built by our community members</p>
            </div>
            <div class="projects-filters">
                <button class="filter-btn active">All</button>
                <button class="filter-btn">Web</button>
                <button class="filter-btn">AI/ML</button>
                <button class="filter-btn">Competitive Programming</button>
                <button class="filter-btn">IoT</button>
            </div>
            <div class="events-grid">
                <div class="project-card">
                    <div class="project-image">
                        Project Screenshot
                    </div>
                    <div class="project-body">
                        <h3>Code Mentor Platform</h3>
                        <p>A peer-to-peer mentoring platform connecting experienced coders with beginners for personalized guidance.</p>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">GitHub</a>
                            <a href="#" class="project-link">Live Demo</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        Project Screenshot
                    </div>
                    <div class="project-body">
                        <h3>Algorithm Visualizer</h3>
                        <p>Interactive visualization tool for understanding complex algorithms like Dijkstra's, QuickSort, and Dynamic Programming.</p>
                        <div class="project-tech">
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Canvas API</span>
                            <span class="tech-tag">HTML5</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">GitHub</a>
                            <a href="#" class="project-link">Live Demo</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        Project Screenshot
                    </div>
                    <div class="project-body">
                        <h3>Smart Campus IoT</h3>
                        <p>IoT-based campus management system for monitoring energy usage, occupancy, and environmental conditions.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Arduino</span>
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Firebase</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">GitHub</a>
                            <a href="#" class="project-link">Live Demo</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Alumni Section -->
    <section id="alumni" class="section">
        <div class="container">
            <div class="section-header">
                <h2>Alumni Success Stories</h2>
                <p>Where our community members are making an impact</p>
            </div>
            <div class="vision-cards">
                <div class="vision-card">
                    <h3>AI & Machine Learning</h3>
                    <p>Alumni working at leading AI research labs and companies, developing cutting-edge ML models and applications.</p>
                </div>
                <div class="vision-card">
                    <h3>Cloud Computing</h3>
                    <p>Experts in cloud infrastructure, DevOps, and scalable distributed systems at major tech companies.</p>
                </div>
                <div class="vision-card">
                    <h3>Cybersecurity</h3>
                    <p>Security professionals protecting critical infrastructure and developing next-generation security solutions.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Team Section -->
    <section id="team" class="section" style="background-color: var(--accent);">
        <div class="container">
            <div class="section-header">
                <h2>Meet Our Team</h2>
                <p>Dedicated leaders driving our community forward</p>
            </div>
            <div class="team-grid">
                <div class="team-member">
                    <div class="member-image">
                        Team Member Photo
                    </div>
                    <div class="member-info">
                        <h3>Sarah Johnson</h3>
                        <div class="member-role">Community Lead</div>
                        <p>Organizing events and mentoring new members</p>
                        <div class="social-links">
                            <a href="#" class="social-link">LinkedIn</a>
                            <a href="#" class="social-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image">
                        Team Member Photo
                    </div>
                    <div class="member-info">
                        <h3>Raj Patel</h3>
                        <div class="member-role">Core Member</div>
                        <p>Managing competitive programming initiatives</p>
                        <div class="social-links">
                            <a href="#" class="social-link">LinkedIn</a>
                            <a href="#" class="social-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="team-member">
                    <div class="member-image">
                        Team Member Photo
                    </div>
                    <div class="member-info">
                        <h3>Dr. Emily Chen</h3>
                        <div class="member-role">Faculty Mentor</div>
                        <p>Providing academic guidance and industry connections</p>
                        <div class="social-links">
                            <a href="#" class="social-link">LinkedIn</a>
                            <a href="#" class="social-link">Email</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
        <div class="container">
            <div class="section-header">
                <h2>Get In Touch</h2>
                <p>Have questions or want to join our community?</p>
            </div>
            <div class="contact-container">
                <div class="contact-form">
                    <form id="contactForm">
                        <div class="form-group">
                            <input type="text" placeholder="Your Name" required>
                        </div>
                        <div class="form-group">
                            <input type="email" placeholder="Your Email" required>
                        </div>
                        <div class="form-group">
                            <textarea placeholder="Your Message" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Message</button>
                    </form>
                </div>
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <p><strong>Email:</strong> community@gprec.ac.in</p>
                    <p><strong>Location:</strong> G. Pulla Reddy Engineering College</p>
                    <p><strong>Social:</strong> Follow us on GitHub and LinkedIn</p>
                    <div class="map-placeholder">
                        College Location Map
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">CodeChef Community</div>
                <ul class="footer-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#events">Events</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#team">Team</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            <div style="margin-top: 20px; opacity: 0.8;">
                © 2026 CodeChef Community Portal. All rights reserved.
            </div>
        </div>
    </footer>

    <!-- Scroll to Top Button -->
    <div class="scroll-to-top" id="scrollTopBtn">
        ↑
    </div>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    window.scrollTo({
                        top: target.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Scroll to top button functionality
        const scrollTopBtn = document.getElementById('scrollTopBtn');
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 300) {
                scrollTopBtn.classList.add('show');
            } else {
                scrollTopBtn.classList.remove('show');
            }
        });

        scrollTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // Form submission handling
        const contactForm = document.getElementById('contactForm');
        if (contactForm) {
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
                // In a real implementation, this would send the form data
                alert('Thank you for your message! We will get back to you soon.');
                contactForm.reset();
            });
        }

        // Filter buttons functionality
        const filterButtons = document.querySelectorAll('.filter-btn');
        filterButtons.forEach(button => {
            button.addEventListener('click', function() {
                filterButtons.forEach(btn => btn.classList.remove('active'));
                this.classList.add('active');
                // In a real implementation, this would filter the displayed items
            });
        });
    </script>
</body>
</html>


