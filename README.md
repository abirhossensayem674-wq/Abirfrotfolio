# Abirfrotfolio
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abir's Portfolio</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <header>
        <div class="container">
            <h1>Hi, I'm Abir</h1>
            <p>Aspiring Programmer & Freelancer</p>
            <nav>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
            </nav>
        </div>
    </header>

    <section id="about" class="fade-in">
        <div class="container">
            <h2>About Me</h2>
            <p>I am a 16-year-old learner exploring programming, trading, and building amazing things online.</p>
        </div>
    </section>

    <section id="projects" class="fade-in">
        <div class="container">
            <h2>Projects</h2>
            <ul>
                <li>Simple Calculator App</li>
                <li>Personal Blog Website</li>
                <li>Trading Dashboard (Demo)</li>
            </ul>
        </div>
    </section>

    <section id="contact" class="fade-in">
        <div class="container">
            <h2>Contact Me</h2>
            <form id="contactForm">
                <input type="text" placeholder="Your Name" required>
                <input type="email" placeholder="Your Email" required>
                <textarea placeholder="Your Message" required></textarea>
                <button type="submit" class="glow">Send</button>
            </form>
        </div>
    </section>

    <footer>
        <p>© 2025 Abir Hossen Sayem</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
/* General */
body {
    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    background: #111;
    color: #fff;
    scroll-behavior: smooth;
}

.container {
    max-width: 800px;
    margin: auto;
    padding: 20px;
}

/* Header */
header {
    background: linear-gradient(135deg, #1a73e8, #00c6ff);
    text-align: center;
    padding: 60px 20px;
}

header h1 {
    font-size: 3em;
    margin: 0;
    animation: fadeDown 1s ease forwards;
}

header p {
    font-size: 1.2em;
    margin: 10px 0 20px;
}

header nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
    font-weight: bold;
    transition: 0.3s;
}

header nav a:hover {
    color: #fffb00;
}

/* Sections */
section {
    padding: 50px 0;
}

section h2 {
    text-align: center;
    margin-bottom: 20px;
    font-size: 2em;
}

/* Contact Form */
form {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

input, textarea {
    padding: 12px;
    font-size: 16px;
    border: none;
    border-radius: 8px;
}

button.glow {
    padding: 15px;
    background: #1a73e8;
    border: none;
    border-radius: 8px;
    color: white;
    font-size: 18px;
    cursor: pointer;
    box-shadow: 0 0 20px #1a73e8, 0 0 40px #00c6ff, 0 0 60px #1a73e8;
    transition: 0.3s;
}

button.glow:hover {
    box-shadow: 0 0 30px #fffb00, 0 0 60px #fffb00, 0 0 90px #fffb00;
}

/* Footer */
footer {
    text-align: center;
    padding: 20px;
    background: #222;
}

/* Animations */
.fade-in {
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 1s forwards;
}

@keyframes fadeUp {
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes fadeDown {
    from { transform: translateY(-50px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
}

/* Responsive */
@media (max-width: 600px) {
    header h1 { font-size: 2.2em; }
    section h2 { font-size: 1.5em; }
}
// Contact Form Alert
document.getElementById("contactForm").addEventListener("submit", function(e){
    e.preventDefault();
    alert("Thanks for contacting me! I will reply soon.");
    this.reset();
});

// Scroll Animation Delay
window.addEventListener("scroll", function() {
    const sections = document.querySelectorAll(".fade-in");
    const triggerBottom = window.innerHeight * 0.9;

    sections.forEach(section => {
        const sectionTop = section.getBoundingClientRect().top;
        if(sectionTop < triggerBottom){
            section.style.opacity = "1";
            section.style.transform = "translateY(0)";
        }
    });
});
