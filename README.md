<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lucas Kemper - GitHub Profile</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        :root {
            --primary-color: #ff3366;
            --secondary-color: #6e1b9c;
            --background-color: #0d1117;
            --text-color: #c9d1d9;
            --card-bg: rgba(255, 255, 255, 0.05);
            --hover-transition: all 0.3s ease;
        }

        body {
            background-color: var(--background-color);
            color: var(--text-color);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            margin: 0;
            padding: 20px;
            line-height: 1.6;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Enhanced Header Section */
        .header-section {
            display: grid;
            grid-template-columns: 1fr auto;
            gap: 30px;
            margin-bottom: 50px;
            align-items: center;
        }

        .header-content {
            position: relative;
        }

        .profile-title {
            font-size: 3.5em;
            margin: 0;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: titleGlow 2s ease-in-out infinite;
        }

        @keyframes titleGlow {
            0%, 100% { text-shadow: 0 0 20px rgba(255, 51, 102, 0.3); }
            50% { text-shadow: 0 0 30px rgba(255, 51, 102, 0.5); }
        }

        /* Enhanced Tech Stack Grid */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 25px;
            padding: 30px;
            background: var(--card-bg);
            border-radius: 15px;
            margin: 40px 0;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            border-radius: 10px;
            transition: var(--hover-transition);
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: -100%;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            opacity: 0.1;
            transition: var(--hover-transition);
        }

        .tech-item:hover::before {
            top: 0;
        }

        .tech-item:hover {
            transform: translateY(-5px);
        }

        /* Enhanced Project Showcase */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .project-card {
            position: relative;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            transition: var(--hover-transition);
            overflow: hidden;
        }

        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            transform: scaleX(0);
            transition: var(--hover-transition);
        }

        .project-card:hover::after {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        /* Enhanced Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            margin: 40px 0;
        }

        .stat-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: var(--hover-transition);
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            opacity: 0.1;
            transition: var(--hover-transition);
        }

        .stat-card:hover::before {
            left: 0;
        }

        /* Enhanced Activity Graph */
        .activity-section {
            margin: 40px 0;
            padding: 30px;
            background: var(--card-bg);
            border-radius: 15px;
            position: relative;
            overflow: hidden;
        }

        .activity-graph {
            width: 100%;
            height: 300px;
            position: relative;
        }

        /* Contribution Calendar */
        .contribution-calendar {
            display: grid;
            grid-template-columns: repeat(52, 1fr);
            gap: 3px;
            padding: 20px;
            background: var(--card-bg);
            border-radius: 15px;
        }

        .calendar-day {
            width: 100%;
            padding-top: 100%;
            background: var(--card-bg);
            border-radius: 2px;
            transition: var(--hover-transition);
        }

        .calendar-day:hover {
            transform: scale(1.2);
        }

        /* Contact Section */
        .contact-section {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 40px 0;
            padding: 30px;
            background: var(--card-bg);
            border-radius: 15px;
        }

        .contact-button {
            padding: 15px 30px;
            border-radius: 10px;
            text-decoration: none;
            color: var(--text-color);
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            transition: var(--hover-transition);
            position: relative;
            overflow: hidden;
        }

        .contact-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        @media (max-width: 768px) {
            .header-section {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Enhanced Header Section -->
        <div class="header-section">
            <div class="header-content">
                <h1 class="profile-title">Lucas Kemper</h1>
                <p class="role">[ Quant Finance & AI Researcher | Quantitative Developer | Financial Engineer ]</p>
            </div>
            <img src="/api/placeholder/150/150" alt="Profile" class="profile-image"/>
        </div>

        <!-- Enhanced Tech Stack -->
        <div class="tech-grid">
            <div class="tech-item">
                <img src="/api/placeholder/50/50" alt="Python"/>
                <span>Python</span>
                <div class="tech-level" style="width: 90%"></div>
            </div>
            <!-- Add more tech items -->
        </div>

        <!-- Enhanced Projects Showcase -->
        <div class="projects-grid">
            <div class="project-card">
                <img src="/api/placeholder/400/200" alt="Portfolio Risk MC" class="project-image"/>
                <h3>Portfolio Risk MC</h3>
                <p>Advanced Monte Carlo simulation tool for portfolio risk analysis, featuring real-time market data integration.</p>
                <div class="project-tech">
                    <span>Python</span>
                    <span>NumPy</span>
                    <span>Pandas</span>
                </div>
            </div>
            <div class="project-card">
                <img src="/api/placeholder/400/200" alt="LLM Finance Analysis" class="project-image"/>
                <h3>LLM Finance Analysis</h3>
                <p>Cutting-edge financial analysis platform leveraging Large Language Models for market insights and predictions.</p>
                <div class="project-tech">
                    <span>PyTorch</span>
                    <span>Transformers</span>
                    <span>FastAPI</span>
                </div>
            </div>
        </div>

        <!-- Enhanced Stats Section -->
        <div class="stats-grid">
            <div class="stat-card">
                <h3>Contributions</h3>
                <img src="/api/placeholder/300/150" alt="Contribution Stats"/>
            </div>
            <div class="stat-card">
                <h3>Languages</h3>
                <img src="/api/placeholder/300/150" alt="Language Stats"/>
            </div>
            <div class="stat-card">
                <h3>Achievements</h3>
                <img src="/api/placeholder/300/150" alt="Achievement Stats"/>
            </div>
        </div>

        <!-- Enhanced Activity Section -->
        <div class="activity-section">
            <h2>Contribution Activity</h2>
            <div class="activity-graph">
                <img src="/api/placeholder/1200/300" alt="Activity Graph"/>
            </div>
        </div>

        <!-- Contact Section -->
        <div class="contact-section">
            <a href="https://linkedin.com/in/lucas-kemper" class="contact-button">
                LinkedIn
            </a>
            <a href="mailto:contact@lucaskemper.com" class="contact-button">
                Email
            </a>
            <a href="https://www.lucaskemper.com" class="contact-button">
                Portfolio
            </a>
        </div>
    </div>

    <script>
        // Initialize interactive elements
        document.addEventListener('DOMContentLoaded', () => {
            // Add hover effects to tech items
            const techItems = document.querySelectorAll('.tech-item');
            techItems.forEach(item => {
                item.addEventListener('mouseover', () => {
                    item.style.transform = 'scale(1.1)';
                });
                item.addEventListener('mouseout', () => {
                    item.style.transform = 'scale(1)';
                });
            });

            // Add scroll reveal animation
            const revealElements = document.querySelectorAll('.project-card, .stat-card');
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            });

            revealElements.forEach(element => {
                element.style.opacity = '0';
                element.style.transform = 'translateY(20px)';
                element.style.transition = 'all 0.6s ease-out';
                observer.observe(element);
            });
        });
    </script>
</body>
</html>
