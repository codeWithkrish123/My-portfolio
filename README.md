# My-portfolio

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>John Doe - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Header Section */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: white;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #ffd700;
            transform: translateY(-2px);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #ffd700;
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding-top: 80px;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out;
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        .hero-content .description {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            animation: fadeInUp 1s ease-out 0.6s both;
        }

        .cta-button {
            background: #ffd700;
            color: #333;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.9s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.4);
        }

        /* About Section */
        .about {
            padding: 5rem 0;
            background: #f8f9fa;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 4rem;
            align-items: center;
        }

        .about-image {
            text-align: center;
        }

        .about-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 5px solid #667eea;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: #666;
            line-height: 1.8;
        }

        /* Skills Section */
        .skills {
            padding: 5rem 0;
            background: white;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-item {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s ease;
            border-left: 5px solid #667eea;
        }

        .skill-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #667eea;
        }

        .skill-item h3 {
            margin-bottom: 1rem;
            color: #333;
        }

        .skill-progress {
            background: #e9ecef;
            height: 10px;
            border-radius: 5px;
            overflow: hidden;
            margin-top: 1rem;
        }

        .skill-progress-bar {
            height: 100%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 5px;
            transition: width 2s ease-in-out;
        }

        /* Projects Section */
        .projects {
            padding: 5rem 0;
            background: #f8f9fa;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0,0,0,0.15);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 2rem;
        }

        .project-content h3 {
            margin-bottom: 1rem;
            color: #333;
        }

        .project-content p {
            color: #666;
            margin-bottom: 1.5rem;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            background: #667eea;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            text-decoration: none;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: #764ba2;
            transform: translateY(-2px);
        }

        /* Resume Section */
        .resume {
            padding: 5rem 0;
            background: white;
            text-align: center;
        }

        .resume-content {
            max-width: 600px;
            margin: 0 auto;
        }

        .resume-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #666;
        }

        .resume-button {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            text-decoration: none;
            display: inline-block;
            transition: all 0.3s ease;
        }

        .resume-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(102, 126, 234, 0.4);
        }

        /* Contact Section */
        .contact {
            padding: 5rem 0;
            background: #f8f9fa;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-top: 3rem;
        }

        .contact-info {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
        }

        .contact-icon {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1rem;
            font-size: 1.2rem;
        }

        .contact-form {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #333;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .submit-btn {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        /* Footer Section */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 3rem 0 1rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .social-link {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .footer-text {
            border-top: 1px solid #555;
            padding-top: 2rem;
            color: #ccc;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            animation: fadeInUp 1s ease-out;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .social-links {
                gap: 1rem;
            }

            .container {
                padding: 0 1rem;
            }
        }

        @media (max-width: 480px) {
            .hero-content h1 {
                font-size: 2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .about-img {
                width: 200px;
                height: 200px;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header>
        <nav>
            <a href="#home" class="logo">Krish sah</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#resume">Resume</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Krish Sah</h1>
            <p class="subtitle">Web developer</p>
            <p class="description">A Front-End Developer is responsible for creating engaging, user-friendly web interfaces using modern web technologies. They work closely with designers and back-end developers to turn visual designs into interactive, responsive, and performant websites or web applications.</p>
            <a href="#contact" class="cta-button">Get In Touch</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-image">
                    <img src="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 300 300'><circle fill='%23667eea' cx='150' cy='150' r='150'/><circle fill='%23fff' cx='150' cy='120' r='40'/><circle fill='%23fff' cx='150' cy='200' r='60'/></svg>" alt="John Doe" class="about-img">
                </div>
                <div class="about-text">
                    <p>Hello! I'm Krish sah, a passionate Web Developer with over less than 1 years of experience in creating digital solutions that make a difference. I love turning complex problems into simple, beautiful designs.</p>
                    <p>My expertise spans across modern web technologies including React, Node.js, I'm always eager to learn new technologies and take on challenging projects that push the boundaries of what's possible.</p>
                    <p>When I'm not coding, you can find me exploring new design trends, contributing to open-source projects, or enjoying a good cup of coffee while planning my next creative endeavor.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSFBDpP5C5t_t8FjbMu-rjqndyjCmaoKMNTjA&s" alt=""height="210px"width="210px"></div>
                    <h3>HTML</h3>
                    <p>Hyper text markup Language</p>
    
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 100%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRTwzDfejQjrtyuTLtbhl78_QUBEtG86gBq7cIkjmtkpMgUuC7A6V9-l-UmgsX0mcz6wFk&usqp=CAU" alt=""height="210px"width="210px"></div>
                    <h3>CSS</h3>
                    <p>Cast style scading</p>

                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 100%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTHihIzOkBdMqtxVw0DwFs3bMfGXkA91iifayL3sxTyhJHTMWK_D0A_BQkSYQ1gO49iUNk&usqp=CAU" alt=""height="210px"width="210px"></div>
                    <h3>Javacript</h3>
                    <p>low-level-programing language</p>                    
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 80%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://images.icon-icons.com/2108/PNG/512/react_icon_130845.png" alt=""height="210px"width="210px"></div>
                    <h3>React</h3>
                    <p>React is a javascript library</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 70%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT_UUFIJtVAwXQo3ICnfQJy3BrAX8os-HChbyxvT2_H6xUL3ekkr8oxVdNkLSHTsxn6pTo&usqp=CAU" alt=""height="210px"width="210px"></div>
                    <h3>Node js</h3>
                    <p>Node.js is a JavaScript runtime environment- to build server-side and networking</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 60%;"></div>
                    </div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><img src="https://cdn.worldvectorlogo.com/logos/mongodb-icon-1.svg" alt=""height="210px"width="210px"></div>
                    <h3>MongoDB</h3>
                    <p>MongoDB is a popular, open-source, NoSQL database that uses a document-oriented model for storing data</p>
                    <div class="skill-progress">
                        <div class="skill-progress-bar" style="width: 55%;"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title">My Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image"><img src="https://st2.depositphotos.com/1688079/5651/i/450/depositphotos_56511431-stock-photo-blog-glossy-blue-reflected-square.jpg" alt=""height="380px"width="380px"></div>
                    <div class="project-content">
                        <h3>CSS-BLOG-PROJECT</h3>
                        <p>CSS BLOG PROJECT is made by using HTML and CSS </p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image"><img src="" alt=""></div>
                    <div class="project-content">
                        <h3>Task Management App</h3>
                        <p>A collaborative task management application with real-time updates, built using React, Socket.io, and MongoDB.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">🎵</div>
                    <div class="project-content">
                        <h3>Music Streaming App</h3>
                        <p>A Spotify-like music streaming application with playlist management, search functionality, and audio player controls.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3>Analytics Dashboard</h3>
                        <p>A comprehensive analytics dashboard with interactive charts and real-time data visualization using D3.js and React.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Resume Section -->
    <section id="resume" class="resume">
        <div class="container">
            <h2 class="section-title">Resume</h2>
            <div class="resume-content">
                <p>Interested in learning more about my experience and qualifications? Download my complete resume to see my full professional background, education, and achievements.</p>
                <a href="#" class="resume-button" download>Download Resume</a>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div>
                            <h4>Email</h4>
                            <p>john.doe@email.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div>
                            <h4>Phone</h4>
                            <p>+1 (555) 123-4567</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h4>Location</h4>
                            <p>New York, NY</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">💼</div>
                        <div>
                            <h4>LinkedIn</h4>
                            <p>linkedin.com/in/johndoe</p>
                        </div>
                    </div>
                </div>
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer Section -->
    <footer>
        <div class="footer-content">
            <div class="social-links">
                <a href="#" class="social-link">📘</a>
                <a href="#" class="social-link">🐦</a>
                <a href="#" class="social-link">💼</a>
                <a href="#" class="social-link">📷</a>
                <a href="#" class="social-link">📧</a>
            </div>
            <div class="footer-text">
                <p>&copy; 2025 John Doe. All rights reserved. Built with ❤️ using HTML & CSS only.</p>
            </div>
        </div>
    </footer>
</body>
</html>
