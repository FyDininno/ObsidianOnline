<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cloud Resume</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        header {
            background: #333;
            color: #fff;
            padding: 1rem 0;
            text-align: center;
        }
        header h1 {
            margin: 0;
        }
        section {
            background: #fff;
            padding: 2rem;
            margin: 1rem 0;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            border-bottom: 2px solid #333;
            padding-bottom: 0.5rem;
        }
        .contact-info, .experience, .education {
            margin-bottom: 1.5rem;
        }
        .experience-item, .education-item {
            margin-bottom: 1rem;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>John Doe</h1>
            <p>Cloud Engineer | Software Developer</p>
        </div>
    </header>

    <div class="container">
        <section class="contact-info">
            <h2>Contact Information</h2>
            <p>Email: john.doe@example.com</p>
            <p>Phone: (123) 456-7890</p>
            <p>LinkedIn: <a href="https://linkedin.com/in/johndoe" target="_blank">linkedin.com/in/johndoe</a></p>
            <p>GitHub: <a href="https://github.com/johndoe" target="_blank">github.com/johndoe</a></p>
        </section>

        <section class="intro">
            <h2>About Me</h2>
            <p>Experienced Cloud Engineer with a strong background in software development. Passionate about building scalable cloud infrastructure and optimizing performance. Proven track record in designing and implementing cloud solutions for various applications.</p>
        </section>

        <section class="skills">
            <h2>Skills</h2>
            <ul>
                <li>Cloud Platforms: AWS, Azure, Google Cloud</li>
                <li>Programming Languages: Python, JavaScript, Java</li>
                <li>Infrastructure as Code: Terraform, CloudFormation</li>
                <li>Containerization: Docker, Kubernetes</li>
                <li>CI/CD: Jenkins, GitLab CI</li>
            </ul>
        </section>

        <section class="experience">
            <h2>Experience</h2>
            <div class="experience-item">
                <h3>Senior Cloud Engineer</h3>
                <p><strong>ABC Corp</strong> - City, State</p>
                <p>January 2020 - Present</p>
                <ul>
                    <li>Designed and implemented scalable cloud architectures for client applications.</li>
                    <li>Managed CI/CD pipelines and automated deployment processes.</li>
                    <li>Optimized cloud resources, resulting in 30% cost savings.</li>
                </ul>
            </div>
            <div class="experience-item">
                <h3>Cloud Developer</h3>
                <p><strong>XYZ Inc</strong> - City, State</p>
                <p>June 2017 - December 2019</p>
                <ul>
                    <li>Developed cloud-based solutions and microservices.</li>
                    <li>Worked on serverless architectures using AWS Lambda.</li>
                    <li>Collaborated with cross-functional teams to deliver high-quality software.</li>
                </ul>
            </div>
        </section>

        <section class="education">
            <h2>Education</h2>
            <div class="education-item">
                <h3>Bachelor of Science in Computer Science</h3>
                <p><strong>University Name</strong> - City, State</p>
                <p>Graduated: 2017</p>
            </div>
        </section>
    </div>
</body>
</html>
