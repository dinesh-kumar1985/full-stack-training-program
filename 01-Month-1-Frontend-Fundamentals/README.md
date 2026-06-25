# Month 1: Frontend Fundamentals
## HTML5, CSS3, Responsive Design, and JavaScript Basics

**Duration:** 4 Weeks (26 Days)
**Daily Time Commitment:** 6-8 hours
**Expected Outcome:** Job-ready frontend fundamentals

---

## 🎯 Month 1 Learning Objectives

✅ Master HTML5 semantic structure and best practices
✅ Learn CSS3 styling, animations, and layouts
✅ Understand responsive design principles
✅ Master Flexbox and CSS Grid layouts
✅ Learn Bootstrap 5 for rapid development
✅ Learn Tailwind CSS for utility-first design
✅ JavaScript fundamentals and ES6+ features
✅ DOM manipulation and event handling
✅ Build 8+ projects with industry standards
✅ Deploy projects to GitHub Pages

---

## 📋 Week-by-Week Breakdown

### **Week 1: HTML5 & CSS Fundamentals**

#### **Days 1-2: HTML5 Basics**

**Topics Covered:**
- HTML document structure
- Semantic HTML tags (header, nav, main, section, article, footer, aside)
- Forms and input elements
- Accessibility (alt text, ARIA labels, semantic meaning)
- Meta tags and SEO basics
- Validation and best practices

**Daily Tasks:**
```html
<!-- Task 1: Create semantic HTML structure -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Professional portfolio website">
    <title>My Professional Portfolio</title>
</head>
<body>
    <header>
        <nav role="navigation">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h1>Welcome to My Portfolio</h1>
            <p>Full Stack Web Developer | React | Django</p>
        </section>

        <section id="about">
            <h2>About Me</h2>
            <p>I am a passionate web developer with expertise in modern web technologies.</p>
        </section>

        <section id="projects">
            <h2>Featured Projects</h2>
            <article>
                <h3>E-Commerce Platform</h3>
                <p>Built with React and Django</p>
            </article>
        </section>

        <section id="contact">
            <h2>Get In Touch</h2>
            <form>
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>

                <label for="message">Message:</label>
                <textarea id="message" name="message" rows="5" required></textarea>

                <button type="submit">Send Message</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 My Portfolio. All rights reserved.</p>
        <p><a href="https://github.com/yourname">GitHub</a> | <a href="https://linkedin.com/in/yourname">LinkedIn</a></p>
    </footer>
</body>
</html>
```

**Project 1: Semantic HTML Resume**
- Create a well-structured resume using semantic HTML
- Include all HTML5 best practices
- Add proper meta tags for SEO
- Make it accessible
- Commit to GitHub

---

#### **Days 3-5: CSS3 Styling & Typography**

**Topics Covered:**
- CSS selectors (element, class, ID, pseudo-classes, pseudo-elements)
- Box model (margin, padding, border, content)
- Typography (fonts, sizing, line-height, letter-spacing)
- Colors, backgrounds, and gradients
- CSS variables (custom properties)
- Transitions and basic animations
- Box shadows and effects

**Daily Tasks:**
```css
/* CSS3 Fundamentals */
:root {
    --primary-color: #3498db;
    --secondary-color: #2c3e50;
    --text-color: #333;
    --border-radius: 8px;
    --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    --transition: all 0.3s ease;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    color: var(--text-color);
    background-color: #f5f5f5;
}

header {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: white;
    padding: 2rem 0;
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 100;
}

nav ul {
    list-style: none;
    display: flex;
    gap: 2rem;
    justify-content: center;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: 500;
    transition: var(--transition);
    border-bottom: 2px solid transparent;
}

nav a:hover {
    border-bottom-color: white;
    opacity: 0.8;
}

main section {
    max-width: 1200px;
    margin: 2rem auto;
    padding: 2rem;
    background: white;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

h1, h2, h3 {
    color: var(--primary-color);
    margin-bottom: 1rem;
    font-weight: 600;
}

h1 { font-size: 2.5rem; }
h2 { font-size: 2rem; }
h3 { font-size: 1.5rem; }

button {
    background: var(--primary-color);
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: var(--border-radius);
    cursor: pointer;
    font-size: 1rem;
    font-weight: 600;
    transition: var(--transition);
}

button:hover {
    background: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

button:active {
    transform: translateY(0);
}

form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

input, textarea {
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: var(--border-radius);
    font-family: inherit;
    font-size: 1rem;
    transition: var(--transition);
}

input:focus, textarea:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 5px rgba(52, 152, 219, 0.3);
}

footer {
    background: var(--secondary-color);
    color: white;
    text-align: center;
    padding: 2rem;
    margin-top: 4rem;
}

footer a {
    color: var(--primary-color);
    text-decoration: none;
}

footer a:hover {
    text-decoration: underline;
}
```

**Project 2: Styled Portfolio Website**
- Style the HTML resume with CSS3
- Implement transitions and hover effects
- Use CSS variables for consistent theming
- Add proper spacing and typography
- Commit to GitHub

---

### **Week 2: Responsive Design & Flexbox**

#### **Days 6-7: Responsive Design Principles**

**Topics Covered:**
- Mobile-first design approach
- Media queries and breakpoints
- Viewport meta tag
- Responsive units (rem, em, %, vw, vh)
- Fluid typography
- Responsive images
- Container queries

**Daily Tasks:**
```css
/* Responsive Design Example */

/* Mobile First - Base styles for mobile */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-size: 16px;  /* 1rem = 16px */
}

.container {
    width: 100%;
    padding: 1rem;
    max-width: none;
}

.grid {
    display: grid;
    grid-template-columns: 1fr;  /* Single column on mobile */
    gap: 1rem;
}

img {
    max-width: 100%;
    height: auto;  /* Maintain aspect ratio */
    display: block;
}

/* Tablet - 768px and up */
@media (min-width: 768px) {
    body {
        font-size: 18px;
    }

    .container {
        max-width: 750px;
        margin: 0 auto;
        padding: 2rem;
    }

    .grid {
        grid-template-columns: 1fr 1fr;  /* Two columns */
    }
}

/* Desktop - 1024px and up */
@media (min-width: 1024px) {
    body {
        font-size: 18px;
    }

    .container {
        max-width: 1000px;
    }

    .grid {
        grid-template-columns: 1fr 1fr 1fr;  /* Three columns */
    }
}

/* Large Desktop - 1440px and up */
@media (min-width: 1440px) {
    .container {
        max-width: 1400px;
    }
}

/* Landscape phones */
@media (max-height: 500px) and (orientation: landscape) {
    header {
        padding: 0.5rem 0;
    }
}

/* Print styles */
@media print {
    body {
        font-size: 12pt;
        color: black;
        background: white;
    }

    nav, footer {
        display: none;
    }
}
```

**Project 3: Responsive Landing Page**
- Create a single-page marketing website
- Implement mobile-first responsive design
- Test on mobile, tablet, and desktop sizes
- Use proper media queries
- Add responsive images
- Optimize for all screen sizes
- Deploy to GitHub Pages

---

#### **Days 8-10: Flexbox Mastery**

**Topics Covered:**
- Flex container and flex items
- justify-content (flex-start, center, space-between, space-around, space-evenly)
- align-items (stretch, center, flex-start, flex-end, baseline)
- align-content
- flex-direction (row, column)
- flex-wrap and flex-flow
- gap property for spacing
- flex-grow, flex-shrink, flex-basis
- flex shorthand

**Daily Tasks:**
```css
/* Flexbox Examples */

/* 1. Navigation with Flexbox */
nav {
    display: flex;
    justify-content: space-between;  /* Logo on left, menu on right */
    align-items: center;
    padding: 1rem;
    background-color: #333;
}

nav .logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: white;
}

nav ul {
    display: flex;
    gap: 2rem;
    list-style: none;
}

nav a {
    color: white;
    text-decoration: none;
}

/* 2. Card Grid with Flexbox */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    justify-content: center;
}

.card {
    flex: 1 1 300px;  /* grow, shrink, basis */
    max-width: 350px;
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* 3. Centered Content */
.hero {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
}

/* 4. Space Between Layout (Header) */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
}

.header-left {
    flex: 1;
}

.header-right {
    flex: 1;
    text-align: right;
}

.header-center {
    flex: 1;
    text-align: center;
}

/* 5. Vertical Centering */
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

/* 6. Responsive Flexbox */
.flex-responsive {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

@media (min-width: 768px) {
    .flex-responsive {
        flex-direction: row;
    }

    .flex-responsive > * {
        flex: 1;
    }
}

/* 7. Flex Items Alignment */
.flex-container {
    display: flex;
    gap: 1rem;
}

.flex-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;  /* Content spread vertically */
}
```

**Practice Exercises:**
- Build navigation header with logo and menu
- Create responsive card grid
- Build hero section with centered content
- Create footer with flex layout
- Build sidebar + main content layout

**Project 4: Dashboard Layout with Flexbox**
- Create responsive dashboard/app layout
- Header with navigation
- Sidebar and main content area
- Multiple card layouts
- Responsive on all screen sizes

---

### **Week 3: CSS Grid & Modern Layouts**

#### **Days 11-12: CSS Grid Mastery**

**Topics Covered:**
- Grid container and grid items
- grid-template-columns and grid-template-rows
- grid-column and grid-row spanning
- gap and column-gap/row-gap
- Named grid areas
- auto-fit and auto-fill
- minmax() and fit-content()
- Grid auto-flow

**Daily Tasks:**
```css
/* CSS Grid Examples */

/* 1. Basic Grid Layout */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: auto 1fr auto;
    gap: 1rem;
    min-height: 100vh;
}

.header {
    grid-column: 1 / -1;  /* Span all columns */
    background: #333;
    color: white;
    padding: 2rem;
}

.sidebar {
    grid-column: 1;
    background: #f5f5f5;
}

.main-content {
    grid-column: 2 / -1;
}

.footer {
    grid-column: 1 / -1;
    background: #333;
    color: white;
    padding: 1rem;
}

/* 2. Named Grid Areas */
.layout {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    gap: 1rem;
    grid-template-areas:
        "header header header"
        "sidebar content ads"
        "footer footer footer";
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.ads { grid-area: ads; }
.footer { grid-area: footer; }

/* 3. Responsive Grid */
@media (max-width: 768px) {
    .layout {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "sidebar"
            "content"
            "ads"
            "footer";
    }
}

/* 4. Auto-fit for Cards */
.auto-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1rem;
}

/* 5. Auto-fill vs Auto-fit */
.auto-fill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
}

/* 6. Complex Grid Layout */
.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
}

.gallery-item:nth-child(1) {
    grid-column: span 2;
    grid-row: span 2;
}

.gallery-item:nth-child(2) {
    grid-column: span 2;
}
```

**Project 5: Multi-Layout Website**
- Create blog/portfolio with multiple layouts
- Hero section with grid
- Features section with auto-fit
- Gallery with complex grid
- Responsive grid on mobile

---

#### **Days 13-14: Bootstrap 5 & Tailwind CSS**

**Topics Covered - Bootstrap 5:**
- Bootstrap grid system (12-column)
- Pre-built components (buttons, cards, modals, navbars)
- Utility classes (spacing, sizing, colors)
- Responsive breakpoints
- Typography utilities
- Forms and validation

**Bootstrap 5 Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Portfolio</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark sticky-top">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My Portfolio</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link active" href="#">Home</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Projects</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="py-5 text-center bg-primary text-white">
        <div class="container">
            <h1 class="display-4 mb-4">Welcome to My Portfolio</h1>
            <p class="lead mb-4">Full Stack Web Developer</p>
            <button class="btn btn-light btn-lg">View My Work</button>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="py-5">
        <div class="container">
            <h2 class="text-center mb-5">Featured Projects</h2>
            <div class="row g-4">
                <div class="col-md-6 col-lg-4">
                    <div class="card h-100">
                        <img src="https://via.placeholder.com/300" class="card-img-top" alt="Project 1">
                        <div class="card-body">
                            <h5 class="card-title">E-Commerce Platform</h5>
                            <p class="card-text">Built with React and Django REST API</p>
                            <a href="#" class="btn btn-primary">View Project</a>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="card h-100">
                        <img src="https://via.placeholder.com/300" class="card-img-top" alt="Project 2">
                        <div class="card-body">
                            <h5 class="card-title">Task Management App</h5>
                            <p class="card-text">React with Redux Toolkit</p>
                            <a href="#" class="btn btn-primary">View Project</a>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="card h-100">
                        <img src="https://via.placeholder.com/300" class="card-img-top" alt="Project 3">
                        <div class="card-body">
                            <h5 class="card-title">Weather Dashboard</h5>
                            <p class="card-text">JavaScript, Fetch API</p>
                            <a href="#" class="btn btn-primary">View Project</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="py-5 bg-light">
        <div class="container">
            <h2 class="text-center mb-5">Get In Touch</h2>
            <div class="row justify-content-center">
                <div class="col-md-6">
                    <form>
                        <div class="mb-3">
                            <label for="name" class="form-label">Name</label>
                            <input type="text" class="form-control" id="name" required>
                        </div>
                        <div class="mb-3">
                            <label for="email" class="form-label">Email</label>
                            <input type="email" class="form-control" id="email" required>
                        </div>
                        <div class="mb-3">
                            <label for="message" class="form-label">Message</label>
                            <textarea class="form-control" id="message" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary w-100">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-4">
        <p>&copy; 2026 My Portfolio. All rights reserved.</p>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

**Topics Covered - Tailwind CSS:**
- Utility-first CSS approach
- Common utility classes
- Responsive prefixes (sm:, md:, lg:, xl:)
- Dark mode
- Custom configuration

**Tailwind CSS Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tailwind Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50">
    <!-- Navigation -->
    <nav class="bg-white shadow-md sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
            <h1 class="text-2xl font-bold text-gray-800">Portfolio</h1>
            <ul class="flex gap-6">
                <li><a href="#" class="text-gray-600 hover:text-gray-900 transition">Home</a></li>
                <li><a href="#" class="text-gray-600 hover:text-gray-900 transition">Projects</a></li>
                <li><a href="#" class="text-gray-600 hover:text-gray-900 transition">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="bg-gradient-to-r from-blue-500 to-purple-600 text-white py-20">
        <div class="max-w-7xl mx-auto text-center px-4">
            <h2 class="text-5xl font-bold mb-4">Welcome to My Portfolio</h2>
            <p class="text-xl mb-8">Full Stack Web Developer</p>
            <button class="bg-white text-blue-600 px-8 py-3 rounded-lg font-bold hover:bg-gray-100 transition">
                View My Work
            </button>
        </div>
    </section>

    <!-- Projects Grid -->
    <section class="max-w-7xl mx-auto px-4 py-16">
        <h2 class="text-4xl font-bold text-center mb-12">Featured Projects</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Project Card -->
            <div class="bg-white rounded-lg overflow-hidden shadow-lg hover:shadow-xl transition">
                <img src="https://via.placeholder.com/300" alt="Project 1" class="w-full h-48 object-cover">
                <div class="p-6">
                    <h3 class="text-xl font-bold mb-2">E-Commerce Platform</h3>
                    <p class="text-gray-600 mb-4">React + Django REST API</p>
                    <a href="#" class="text-blue-600 font-bold hover:text-blue-800">View Project →</a>
                </div>
            </div>

            <!-- More cards... -->
        </div>
    </section>

    <!-- Contact Form -->
    <section class="bg-gray-100 py-16">
        <div class="max-w-2xl mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-12">Get In Touch</h2>
            <form class="bg-white p-8 rounded-lg shadow-lg">
                <div class="mb-4">
                    <label class="block text-gray-700 font-bold mb-2">Name</label>
                    <input type="text" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500" required>
                </div>
                <div class="mb-4">
                    <label class="block text-gray-700 font-bold mb-2">Email</label>
                    <input type="email" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500" required>
                </div>
                <div class="mb-6">
                    <label class="block text-gray-700 font-bold mb-2">Message</label>
                    <textarea class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:outline-none focus:border-blue-500" rows="5" required></textarea>
                </div>
                <button type="submit" class="w-full bg-blue-600 text-white font-bold py-2 px-4 rounded-lg hover:bg-blue-700 transition">
                    Send Message
                </button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white text-center py-8">
        <p>&copy; 2026 My Portfolio. All rights reserved.</p>
    </footer>
</body>
</html>
```

**Project 6: Bootstrap Portfolio**
- Create professional portfolio using Bootstrap 5
- Use Bootstrap grid system
- Implement Bootstrap components
- Responsive on all devices

**Project 7: Tailwind Portfolio**
- Recreate portfolio using Tailwind CSS
- Use utility-first approach
- Implement responsive design
- Add dark mode support

---

### **Week 4: JavaScript Fundamentals & DOM**

#### **Days 15-17: JavaScript Basics**

**Topics Covered:**
- Variables (var, let, const)
- Data types (string, number, boolean, object, array, null, undefined)
- Operators (arithmetic, comparison, logical, assignment)
- Control flow (if/else, switch, ternary)
- Loops (for, while, do-while, for...of, forEach)
- Functions (function declaration, arrow functions, IIFE)
- Scope and hoisting
- Closures
- ES6+ features (arrow functions, destructuring, spread operator, template literals)

**Daily Tasks:**
```javascript
// JavaScript Fundamentals

// 1. Variables and Data Types
const firstName = "John";        // String
let age = 25;                    // Number
var isStudent = true;            // Boolean (avoid using var)
const hobbies = ['reading', 'coding', 'gaming'];  // Array
const person = {                 // Object
    name: 'John',
    age: 25,
    city: 'New York'
};

console.log(typeof firstName);   // "string"
console.log(typeof age);         // "number"

// 2. Operators
const sum = 10 + 5;              // Arithmetic
const difference = 10 - 5;
const product = 10 * 5;
const quotient = 10 / 5;
const remainder = 10 % 3;
const power = 2 ** 3;            // Exponentiation

const isGreater = 10 > 5;        // Comparison
const isEqual = 10 === '10';     // Strict comparison (false)
const isLoose = 10 == '10';      // Loose comparison (true)

const result = true && false;    // Logical AND
const orResult = true || false;  // Logical OR
const notResult = !true;         // Logical NOT

// 3. Control Flow
if (age >= 18) {
    console.log('Adult');
} else if (age >= 13) {
    console.log('Teenager');
} else {
    console.log('Child');
}

// Ternary operator
const status = age >= 18 ? 'Adult' : 'Minor';

// Switch statement
switch (age) {
    case 25:
        console.log('You are 25');
        break;
    case 30:
        console.log('You are 30');
        break;
    default:
        console.log('Other age');
}

// 4. Loops
for (let i = 0; i < 10; i++) {
    console.log(i);
}

let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}

hobbies.forEach(hobby => {
    console.log(hobby);
});

for (let hobby of hobbies) {
    console.log(hobby);
}

// 5. Array Methods
const numbers = [1, 2, 3, 4, 5];

const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

const evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // [2, 4]

const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15

const found = numbers.find(num => num > 3);
console.log(found); // 4

// 6. Functions
function greet(name) {
    return `Hello, ${name}!`;
}

const greetArrow = (name) => `Hello, ${name}!`;
const add = (a, b) => a + b;

// 7. Destructuring
const { name, age: personAge } = person;
const [first, second, ...rest] = [1, 2, 3, 4, 5];

// 8. Spread Operator
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];  // [1, 2, 3, 4, 5]
const merged = { ...person, city: 'Boston' };

// 9. Closures
function outer() {
    const message = 'I am outer';
    
    function inner() {
        console.log(message);
    }
    
    return inner;
}

const myFunc = outer();
myFunc(); // "I am outer"

// 10. Template Literals
const name = 'John';
const greeting = `Hello, ${name}! You are ${age} years old.`;
```

**Practice Exercises:**
- Create calculator functions
- Build sorting and filtering functions
- Practice array manipulation
- String operations
- Object methods

---

#### **Days 18-20: DOM Manipulation & Events**

**Topics Covered:**
- Selecting DOM elements (getElementById, querySelector, etc.)
- Modifying DOM properties (textContent, innerHTML, innerText)
- Modifying attributes
- Class manipulation
- Style manipulation
- Creating and removing elements
- Event listeners and handlers
- Event propagation (bubbling, capturing)
- Event delegation
- Form handling

**Daily Tasks:**
```javascript
// DOM Manipulation

// 1. Selecting Elements
const element = document.getElementById('my-id');
const elements = document.getElementsByClassName('my-class');
const allDivs = document.getElementsByTagName('div');

const queryElement = document.querySelector('.my-class');
const queryElements = document.querySelectorAll('.my-class');

// 2. Modifying Content
element.textContent = 'New Text';
element.innerHTML = '<p>New HTML</p>';
element.innerText = 'New Inner Text';

// 3. Modifying Attributes
element.setAttribute('data-id', '123');
const id = element.getAttribute('data-id');
element.removeAttribute('data-id');
element.hasAttribute('data-id');

// 4. Class Manipulation
element.classList.add('active');
element.classList.remove('active');
element.classList.toggle('active');
element.classList.contains('active');

// 5. Style Manipulation
element.style.backgroundColor = 'red';
element.style.fontSize = '20px';
element.style.display = 'none';
element.style.setProperty('--my-color', 'blue');

// 6. Creating Elements
const newDiv = document.createElement('div');
newDiv.textContent = 'New Element';
newDiv.className = 'my-class';
newDiv.id = 'new-id';
document.body.appendChild(newDiv);

const parent = document.getElementById('parent');
const newChild = document.createElement('p');
parent.insertBefore(newChild, parent.firstChild);

// 7. Removing Elements
element.remove();
parent.removeChild(child);

// 8. Event Listeners
const button = document.querySelector('button');
button.addEventListener('click', () => {
    console.log('Button clicked!');
});

button.addEventListener('click', handleClick);
function handleClick(event) {
    console.log('Clicked:', event.target);
}

// Remove event listener
button.removeEventListener('click', handleClick);

// 9. Form Events
const input = document.querySelector('input');
input.addEventListener('input', (e) => {
    console.log('Input value:', e.target.value);
});

input.addEventListener('change', (e) => {
    console.log('Input changed:', e.target.value);
});

input.addEventListener('focus', () => {
    console.log('Input focused');
});

input.addEventListener('blur', () => {
    console.log('Input blurred');
});

// 10. Form Submission
const form = document.querySelector('form');
form.addEventListener('submit', (e) => {
    e.preventDefault();  // Prevent default form submission
    const formData = new FormData(form);
    const data = Object.fromEntries(formData);
    console.log(data);
});

// 11. Event Delegation
const container = document.querySelector('.container');
container.addEventListener('click', (e) => {
    if (e.target.classList.contains('delete-btn')) {
        console.log('Delete button clicked');
        e.target.parentElement.remove();
    }
});

// 12. Keyboard Events
document.addEventListener('keydown', (e) => {
    console.log('Key pressed:', e.key);
    if (e.key === 'Enter') {
        console.log('Enter key pressed');
    }
});

// 13. Mouse Events
element.addEventListener('mouseenter', () => {
    console.log('Mouse entered');
});

element.addEventListener('mouseleave', () => {
    console.log('Mouse left');
});

element.addEventListener('mousemove', (e) => {
    console.log('Mouse X:', e.clientX, 'Y:', e.clientY);
});
```

**Project 8: Interactive Todo Application**
- Create a todo list app
- Add, delete, mark complete functionality
- Use DOM manipulation
- Event handling for all interactions
- Store data in localStorage
- Professional styling
- Deploy to GitHub Pages

---

#### **Days 21-26: Fetch API & Projects**

**Topics Covered:**
- Promises and async patterns
- Fetch API basics
- GET and POST requests
- Handling JSON responses
- Error handling
- Async/Await syntax
- Real API integration

**Fetch API Examples:**
```javascript
// Fetch API Basics

// 1. Simple GET Request
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// 2. Async/Await GET
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/users');
        if (!response.ok) {
            throw new Error(`HTTP Error: ${response.status}`);
        }
        const data = await response.json();
        console.log(data);
        return data;
    } catch (error) {
        console.error('Error:', error.message);
    }
}

// 3. POST Request
async function createUser(userData) {
    try {
        const response = await fetch('https://api.example.com/users', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': 'Bearer token'
            },
            body: JSON.stringify(userData)
        });
        
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error:', error);
    }
}

// 4. Error Handling
async function robustFetch(url) {
    try {
        const response = await fetch(url);
        
        if (!response.ok) {
            throw new Error(`HTTP ${response.status}: ${response.statusText}`);
        }
        
        const contentType = response.headers.get('content-type');
        if (!contentType?.includes('application/json')) {
            throw new Error('Not JSON');
        }
        
        const data = await response.json();
        return data;
    } catch (error) {
        if (error instanceof TypeError) {
            console.error('Network error:', error.message);
        } else {
            console.error('Error:', error.message);
        }
        throw error;
    }
}

// 5. PUT Request (Update)
async function updateUser(id, userData) {
    const response = await fetch(`https://api.example.com/users/${id}`, {
        method: 'PUT',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(userData)
    });
    return await response.json();
}

// 6. DELETE Request
async function deleteUser(id) {
    const response = await fetch(`https://api.example.com/users/${id}`, {
        method: 'DELETE'
    });
    return await response.json();
}
```

**Project 9: Weather App**
- Fetch weather data from OpenWeatherMap API
- Display current weather and forecast
- Use Async/Await with error handling
- Responsive design
- Deploy to GitHub Pages

**Project 10: GitHub User Finder**
- Search GitHub users using GitHub API
- Display user information and repositories
- Fetch user data via API
- Error handling for invalid users
- Responsive design

**Project 11: Movie Database App**
- Fetch movie data from OMDB API
- Search and filter movies
- Display detailed information
- Responsive grid layout
- Deploy to GitHub Pages

---

## 📝 Month 1 Assignments

### Assignment 1: Complete Personal Portfolio Website
**Requirements:**
- Semantic HTML structure with all best practices
- Fully responsive (mobile, tablet, desktop)
- CSS Grid or Flexbox layout (or combination)
- CSS3 animations and transitions
- Contact form with basic validation
- Professional styling (Bootstrap or Tailwind)
- Navigation menu with smooth scrolling
- Social media links
- Deployed to GitHub Pages
- Clean, organized code with comments

**Submission:**
- GitHub repository with all code
- Live link to deployed site
- README with project description
- Screenshots of responsive design

### Assignment 2: Interactive Web Application Project
**Requirements:**
- HTML5 semantic markup
- CSS3 styling with animations
- JavaScript functionality:
  - DOM manipulation
  - Event handling
  - Data management (localStorage)
  - Fetch API integration (use public API)
- Mobile responsive design
- Error handling
- User feedback (alerts, notifications)

**Submission:**
- GitHub repository
- Live demo link
- Technical documentation
- Code walkthrough video (optional)

---

## 🎓 Month 1 Projects Summary

1. **HTML Resume** - Semantic HTML basics
2. **CSS Portfolio** - Styling and custom CSS
3. **Responsive Landing Page** - Mobile-first responsive design
4. **Flexbox Dashboard** - Flex layout techniques
5. **CSS Grid Layout** - Grid-based complex layouts
6. **Bootstrap Portfolio** - Framework-based development
7. **Tailwind Portfolio** - Utility-first CSS
8. **Todo Application** - DOM manipulation and events
9. **Weather App** - Fetch API integration
10. **GitHub User Finder** - API integration project
11. **Movie Database** - Search and filter with API

---

## 📊 Key Concepts Review

### HTML5
- ✅ Semantic tags for better structure
- ✅ Forms with proper validation
- ✅ Accessibility best practices
- ✅ Meta tags for SEO

### CSS3
- ✅ Box model and layouts
- ✅ Flexbox for 1D layouts
- ✅ CSS Grid for 2D layouts
- ✅ Animations and transitions
- ✅ Responsive design with media queries
- ✅ CSS variables for maintainability

### JavaScript
- ✅ Variables and data types
- ✅ Functions and scope
- ✅ DOM manipulation
- ✅ Event handling
- ✅ Async operations (Promises, Async/Await)
- ✅ Fetch API for HTTP requests
- ✅ ES6+ features

### Frameworks
- ✅ Bootstrap 5 components and utilities
- ✅ Tailwind CSS utility-first approach
- ✅ Responsive design patterns

---

## ✅ Month 1 Progress Checklist

- [ ] Mastered HTML5 semantic structure
- [ ] CSS3 styling complete
- [ ] Responsive design principles understood
- [ ] Flexbox layouts implemented
- [ ] CSS Grid layouts mastered
- [ ] Bootstrap 5 projects completed
- [ ] Tailwind CSS projects completed
- [ ] JavaScript fundamentals solid
- [ ] DOM manipulation working
- [ ] Event handling proficient
- [ ] Fetch API integration working
- [ ] 11 projects completed
- [ ] All projects deployed to GitHub Pages
- [ ] Code quality standards followed
- [ ] GitHub repository organized
- [ ] Portfolio website live

---

## 🎯 Next Steps

**Completed Month 1?** 🎉

👉 **Ready for Month 2:** [Advanced Frontend - React.js & JavaScript ES6+](../02-Month-2-Advanced-Frontend/README.md)

**Month 2 will cover:**
- Advanced JavaScript (ES6+, OOP, Functional Programming)
- React.js fundamentals
- Component architecture
- State management
- Hooks and lifecycle
- Routing with React Router
- Advanced API integration
- Performance optimization

---

**🚀 Keep coding! You're on the path to becoming a professional full-stack developer!**

*Last Updated: June 2026*
