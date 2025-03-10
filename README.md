# HTML-CSS-JS-Components
HTML, CSS and JS components

## Table of Contents

 * [Accordion](#Accordion)
 * [Card Flip](#Card-Flip)
 * [Card Hover Effect](#Card-Hover-Effect)
 * [Card User Profile](#Card-User-Profile)
 * [Chart Bar](#Chart-Bar)
 * [Chart Line Chartjs](#Chart-Line-Chartjs)
 * [Chart Pie](#Chart-Pie)
 * [Dropdown Menu](#Dropdown-Menu)
 * [Dropdown Menu2](#Dropdown-Menu2)
 * [Floating Action Button (FAB)](#Fab)
 * [Form Login Glassmorphism](#Form-Login-Glassmorphism)
 * [Form Multi Step](#Form-Multi-Step)
 * [Image Slider](#Image-Slider)
 * [Loader Circle](#Loader-Circle)
 * [Model Popup](#Model-Popup)
 * [Notification Bell](#Notification-Bell)
 * [Notification Popup](#Notification-Popup)
 * [Progress Circle Bar](#Progress-Circle-Bar) 
 * [Progress Line Bar](#Progress-Line-Bar)
 * [Search Bar](#Search-Bar)
 * [Side Bar Sliding](#Side-Bar-Sliding)
 * [Tab](#Tab) 
 * [Table Data ](#Table-Data)
 * [Table Pricing](#Table-Pricing)
 * [Testionial Slider](#Testionial-Slider)
 * [Toast](#Toast)
 * [Toggle Dark Mode](#Toggle-Dark-Mode) 
 * [Tooltip](#Tooltip)
 


### `Accordion`
```HTML
<div class="accordion">
    <div class="accordion-item">
        <input type="checkbox" id="faq1">
        <label for="faq1">What is this?</label>
        <div class="content">This is an FAQ accordion!</div>
    </div>
</div>

<style>
    .accordion-item {
        border-bottom: 1px solid #ddd;
    }

    .accordion-item label {
        display: block;
        padding: 10px;
        cursor: pointer;
        background: #f7f7f7;
    }

    .content {
        display: none;
        padding: 10px;
    }

    input:checked+label+.content {
        display: block;
    }
</style>
```

### `Card-Flip`
```HTML
<div class="flip-card">
    <div class="flip-inner">
        <div class="flip-front">Front</div>
        <div class="flip-back">Back</div>
    </div>
</div>

<style>
    .flip-card {
        width: 150px;
        height: 150px;
        perspective: 1000px;
    }

    .flip-inner {
        width: 100%;
        height: 100%;
        position: relative;
        transform-style: preserve-3d;
        transition: transform 0.6s;
    }

    .flip-card:hover .flip-inner {
        transform: rotateY(180deg);
    }

    .flip-front,
    .flip-back {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: bold;
        color: white;
    }

    .flip-front {
        background: #ff5722;
    }

    .flip-back {
        background: #3f51b5;
        transform: rotateY(180deg);
    }
</style>
```

### `Card-Hover-Effect`
```HTML
<div class="glass-card">
    <h3>Glass Effect</h3>
    <p>Hover to see the effect!</p>
</div>

<style>
    .glass-card {
        width: 250px;
        padding: 20px;
        border-radius: 12px;
        background: rgba(255, 255, 255, 0.2);
        backdrop-filter: blur(10px);
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        text-align: center;
        transition: 0.3s;
    }

    .glass-card:hover {
        transform: scale(1.05);
        box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
    }
</style>
```

### `Card-User-Profile`
```HTML
<div class="profile-card">
    <img src="https://source.unsplash.com/100x100/?person" alt="User">
    <h3>John Doe</h3>
    <p>Web Developer</p>
    <button>Follow</button>
</div>

<style>
    .profile-card {
        width: 200px;
        text-align: center;
        padding: 20px;
        background: #f7f7f7;
        border-radius: 10px;
    }

    .profile-card img {
        border-radius: 50%;
    }

    button {
        background: #3498db;
        color: white;
        border: none;
        padding: 8px;
        border-radius: 5px;
        cursor: pointer;
    }
</style>
```

### `Chart-Bar`
```HTML
<div class="bar-chart">
    <div class="bar" style="height: 80%;">80%</div>
    <div class="bar" style="height: 60%;">60%</div>
    <div class="bar" style="height: 90%;">90%</div>
</div>

<style>
    .bar-chart {
        display: flex;
        gap: 10px;
        height: 200px;
        align-items: flex-end;
    }

    .bar {
        width: 50px;
        background: #4caf50;
        text-align: center;
        color: white;
        padding: 5px;
        transition: 0.5s;
    }

    .bar:hover {
        background: #2e7d32;
    }
</style>
```

### `Chart-Line-Chartjs`
```HTML
<canvas id="lineChart"></canvas>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
    const ctx = document.getElementById('lineChart').getContext('2d');
    new Chart(ctx, {
        type: 'line',
        data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
            datasets: [{
                label: 'Sales',
                data: [10, 25, 40, 30, 50],
                borderColor: 'blue',
                fill: false
            }]
        }
    });
</script>

<style>
    canvas {
        max-width: 600px;
        margin: auto;
    }
</style>
```

### `Chart-Pie`
```HTML
<div class="pie-chart">
    <svg>
        <circle cx="50" cy="50" r="40"></circle>
        <circle cx="50" cy="50" r="40" class="progress"></circle>
    </svg>
    <span>75%</span>
</div>

<style>
    .pie-chart {
        width: 100px;
        height: 100px;
        position: relative;
    }

    svg {
        width: 100px;
        height: 100px;
        transform: rotate(-90deg);
    }

    circle {
        fill: none;
        stroke-width: 8;
        stroke: #ddd;
    }

    .progress {
        stroke: #4caf50;
        stroke-dasharray: 251;
        stroke-dashoffset: calc(251 - (251 * 75) / 100);
        transition: stroke-dashoffset 1s ease-in-out;
    }

    .pie-chart span {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 16px;
        font-weight: bold;
    }
</style>
```

### `Dropdown-Menu`
```HTML
<div class="dropdown">
    <button class="dropbtn">Dropdown</button>
    <div class="dropdown-content">
        <a href="#">Item 1</a>
        <a href="#">Item 2</a>
        <a href="#">Item 3</a>
    </div>
</div>

<style>
    .dropdown {
        position: relative;
        display: inline-block;
    }

    .dropbtn {
        background: #3498db;
        color: white;
        padding: 12px;
        border: none;
        cursor: pointer;
    }

    .dropdown-content {
        display: none;
        position: absolute;
        background: white;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        min-width: 120px;
        animation: fadeIn 0.3s ease-in-out;
    }

    .dropdown:hover .dropdown-content {
        display: block;
    }

    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(-10px);
        }

        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>
```

### `Dropdown-Menu2`
```HTML
<div class="dropdown">
    <button class="dropdown-btn">Select an Option ▼</button>
    <div class="dropdown-content">
        <a href="#">Option 1</a>
        <a href="#">Option 2</a>
        <a href="#">Option 3</a>
    </div>
</div>

<script>
    document.querySelector(".dropdown-btn").addEventListener("click", function () {
        document.querySelector(".dropdown-content").classList.toggle("show");
    });

    window.onclick = function (e) {
        if (!e.target.matches('.dropdown-btn')) {
            document.querySelector(".dropdown-content").classList.remove("show");
        }
    };
</script>

<style>
    .dropdown {
        position: relative;
        display: inline-block;
    }

    .dropdown-btn {
        background: #3498db;
        color: white;
        padding: 10px;
        border: none;
        cursor: pointer;
    }

    .dropdown-content {
        display: none;
        position: absolute;
        background: white;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        min-width: 150px;
        transition: 0.3s;
    }

    .dropdown-content.show {
        display: block;
    }

    .dropdown-content a {
        display: block;
        padding: 10px;
        color: black;
        text-decoration: none;
    }

    .dropdown-content a:hover {
        background: #ddd;
    }
</style>
```

### `Fab`
```HTML
<div class="fab-container">
    <button class="fab">+</button>
    <div class="fab-menu">
        <button>📩</button>
        <button>📞</button>
        <button>💬</button>
    </div>
</div>

<script>
    document.querySelector(".fab").addEventListener("click", function () {
        document.querySelector(".fab-menu").classList.toggle("open");
    });
</script>

<style>
    .fab-container {
        position: fixed;
    }

    .fab {
        width: 50px;
        height: 50px;
        background: #ff5722;
        color: white;
        font-size: 24px;
        border: none;
        border-radius: 50%;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        cursor: pointer;
        transition: transform 0.3s;
    }

    .fab-menu {
        position: absolute;
        top: 60px;
        right: 0;
        display: flex;
        flex-direction: column;
        gap: 10px;
        opacity: 0;
        visibility: hidden;
        transition: 0.3s;
    }

    .fab-menu.open {
        opacity: 1;
        visibility: visible;
    }

    .fab-menu button {
        width: 40px;
        height: 40px;
        background: #3498db;
        color: white;
        border: none;
        border-radius: 50%;
        cursor: pointer;
    }
</style>
```

### `Form-Login-Glassmorphism`
```HTML
<div class="glass-form">
    <h2>Login</h2>
    <input type="text" placeholder="Username">
    <input type="password" placeholder="Password">
    <button>Login</button>
</div>

<style>
    body {
        background: url('https://source.unsplash.com/1600x900/?abstract') no-repeat center/cover;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .glass-form {
        backdrop-filter: blur(10px);
        background: rgba(255, 255, 255, 0.2);
        padding: 20px;
        border-radius: 12px;
        text-align: center;
    }

    input,
    button {
        display: block;
        width: 100%;
        margin: 10px 0;
        padding: 10px;
        border: none;
        border-radius: 8px;
    }

    button {
        background: #ff9800;
        color: white;
        cursor: pointer;
    }
</style>
```

### `Form-Multi-Step`
```HTML
<div class="multi-step-form">
    <div class="step active">Step 1</div>
    <div class="step">Step 2</div>
    <div class="step">Step 3</div>
</div>

<form id="form">
    <div class="form-step active">
        <label>Name:</label>
        <input type="text">
        <button type="button" onclick="nextStep()">Next</button>
    </div>

    <div class="form-step">
        <label>Email:</label>
        <input type="email">
        <button type="button" onclick="prevStep()">Back</button>
        <button type="button" onclick="nextStep()">Next</button>
    </div>

    <div class="form-step">
        <label>Password:</label>
        <input type="password">
        <button type="button" onclick="prevStep()">Back</button>
        <button type="submit">Submit</button>
    </div>
</form>

<script>
    let stepIndex = 0;
    const steps = document.querySelectorAll(".form-step");
    const indicators = document.querySelectorAll(".step");

    function showStep(index) {
        steps.forEach((step, i) => {
            step.classList.toggle("active", i === index);
            indicators[i].classList.toggle("active", i === index);
        });
    }

    function nextStep() {
        if (stepIndex < steps.length - 1) stepIndex++;
        showStep(stepIndex);
    }

    function prevStep() {
        if (stepIndex > 0) stepIndex--;
        showStep(stepIndex);
    }
</script>

<style>
    .multi-step-form {
        display: flex;
        gap: 10px;
        margin-bottom: 10px;
    }

    .step {
        width: 60px;
        height: 30px;
        text-align: center;
        line-height: 30px;
        background: #ddd;
        border-radius: 5px;
        transition: 0.3s;
    }

    .step.active {
        background: #4caf50;
        color: white;
    }

    .form-step {
        display: none;
    }

    .form-step.active {
        display: block;
    }

    button {
        margin-top: 10px;
        padding: 8px 15px;
        background: #3498db;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
</style>
```

### `Image-Slider`
```HTML
<div class="slider">
    <div class="slides">
        <img src="https://source.unsplash.com/600x300/?nature" alt="Slide 1">
        <img src="https://source.unsplash.com/600x300/?city" alt="Slide 2">
        <img src="https://source.unsplash.com/600x300/?technology" alt="Slide 3">
    </div>
</div>

<script>
    const slides = document.querySelector(".slides");
    let index = 0;

    function nextSlide() {
        index = (index + 1) % 3;
        slides.style.transform = `translateX(${-index * 100}%)`;
    }

    setInterval(nextSlide, 3000);
</script>

<style>
    .slider {
        width: 100%;
        max-width: 600px;
        overflow: hidden;
        border-radius: 10px;
        position: relative;
    }

    .slides {
        display: flex;
        transition: transform 0.5s ease-in-out;
    }

    .slides img {
        width: 100%;
        flex-shrink: 0;
    }
</style>
```

### `Loader-Circle`
```HTML
<div class="loader"></div>

<style>
    .loader {
        width: 50px;
        height: 50px;
        border: 5px solid transparent;
        border-top: 5px solid #ff5722;
        border-radius: 50%;
        animation: spin 1s linear infinite;
    }

    @keyframes spin {
        from {
            transform: rotate(0deg);
        }

        to {
            transform: rotate(360deg);
        }
    }
</style>
```

### `Model-Popup`
```HTML
<button class="open-modal">Open Modal</button>

<div class="modal">
    <div class="modal-content">
        <span class="close-modal">&times;</span>
        <h2>Modal Title</h2>
        <p>This is a fully animated modal popup.</p>
    </div>
</div>

<style>
    .modal {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        opacity: 0;
        visibility: hidden;
        transition: 0.3s;
    }

    .modal-content {
        background: white;
        padding: 20px;
        border-radius: 8px;
        width: 300px;
        text-align: center;
        transform: scale(0.7);
        transition: 0.3s;
    }

    .modal.show {
        opacity: 1;
        visibility: visible;
    }

    .modal.show .modal-content {
        transform: scale(1);
    }

    .close-modal {
        position: absolute;
        right: 15px;
        top: 10px;
        font-size: 20px;
        cursor: pointer;
    }
</style>

<script>
    const modal = document.querySelector(".modal");
    const openBtn = document.querySelector(".open-modal");
    const closeBtn = document.querySelector(".close-modal");

    openBtn.onclick = () => modal.classList.add("show");
    closeBtn.onclick = () => modal.classList.remove("show");
    window.onclick = (e) => {
        if (e.target === modal) modal.classList.remove("show");
    };
</script>
```

### `Notification-Bell`
```HTML
<div class="notification">
    🔔<span class="badge">3</span>
</div>

<style>
    .notification {
        font-size: 24px;
        position: absolute;
        cursor: pointer;
    }

    .badge {
        position: absolute;
        top: -5px;
        right: -5px;
        background: red;
        color: white;
        font-size: 12px;
        padding: 4px 6px;
        border-radius: 50%;
    }
</style>
```

### `Notification-Popup`
```HTML
<button onclick="showNotification()">Show Notification</button>
<div class="notification">✅ Success! Your action was completed.</div>

<script>
    function showNotification() {
        const notification = document.querySelector(".notification");
        notification.classList.add("show");
        setTimeout(() => notification.classList.remove("show"), 3000);
    }
</script>

<style>
    .notification {
        position: fixed;
        bottom: -50px;
        left: 50%;
        transform: translateX(-50%);
        background: green;
        color: white;
        padding: 10px;
        border-radius: 5px;
        transition: 0.3s;
    }

    .notification.show {
        bottom: 20px;
    }
</style>
```

### `Progress-Circle-Bar`
```HTML
<div class="circle-progress">
    <svg>
        <circle cx="50" cy="50" r="40"></circle>
        <circle cx="50" cy="50" r="40" class="progress"></circle>
    </svg>
    <span>75%</span>
</div>

<style>
    .circle-progress {
        width: 100px;
        height: 100px;
        position: relative;
    }

    svg {
        width: 100px;
        height: 100px;
        transform: rotate(-90deg);
    }

    circle {
        fill: none;
        stroke-width: 8;
        stroke: #ddd;
    }

    .progress {
        stroke: #4caf50;
        stroke-dasharray: 251;
        stroke-dashoffset: calc(251 - (251 * 75) / 100);
        transition: stroke-dashoffset 1s ease-in-out;
    }

    .circle-progress span {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 16px;
        font-weight: bold;
    }
</style>
```

### `Progress-Line-Bar`
```HTML
<div class="progress-bar">
    <div class="progress" style="width: 70%;">70%</div>
</div>

<style>
    .progress-bar {
        width: 100%;
        max-width: 400px;
        height: 20px;
        background: #ddd;
        border-radius: 10px;
        overflow: hidden;
        position: relative;
    }

    .progress {
        height: 100%;
        background: #4caf50;
        text-align: center;
        color: white;
        line-height: 20px;
        font-weight: bold;
        transition: width 1s ease-in-out;
    }
</style>
```

### `Search-Bar`
```HTML
<div class="search-bar">
    <input type="text" placeholder="Search...">
    <button>🔍</button>
</div>

<style>
    .search-bar {
        display: flex;
        border: 2px solid #ddd;
        border-radius: 30px;
        overflow: hidden;
        width: 40px;
        transition: 0.4s;
    }

    .search-bar input {
        width: 0;
        border: none;
        padding: 10px;
        outline: none;
        transition: 0.4s;
    }

    .search-bar:hover {
        width: 200px;
    }

    .search-bar:hover input {
        width: 100%;
    }
</style>
```

### `Side-Bar-Sliding`
```HTML
<button onclick="toggleSidebar()">☰ Open Sidebar</button>
<div class="sidebar" id="sidebar">
    <a href="#">Dashboard</a>
    <a href="#">Analytics</a>
    <a href="#">Settings</a>
    <button onclick="toggleSidebar()">Close</button>
</div>

<script>
    function toggleSidebar() {
        document.getElementById("sidebar").classList.toggle("active");
    }
</script>

<style>
    .sidebar {
        position: fixed;
        left: -250px;
        top: 0;
        width: 250px;
        height: 100vh;
        background: #222;
        color: white;
        padding: 20px;
        transition: 0.3s;
    }

    .sidebar.active {
        left: 0;
    }

    .sidebar a,
    .sidebar button {
        display: block;
        padding: 10px;
        color: white;
        text-decoration: none;
        border: none;
        background: none;
        text-align: left;
    }

    .sidebar a:hover,
    .sidebar button:hover {
        background: #444;
    }
</style>
```

### `Tab`
```HTML
<div class="tabs">
    <input type="radio" id="tab1" name="tab" checked>
    <label for="tab1">Tab 1</label>

    <input type="radio" id="tab2" name="tab">
    <label for="tab2">Tab 2</label>

    <input type="radio" id="tab3" name="tab">
    <label for="tab3">Tab 3</label>

    <div class="tab-content" id="content1">Content for Tab 1</div>
    <div class="tab-content" id="content2">Content for Tab 2</div>
    <div class="tab-content" id="content3">Content for Tab 3</div>
</div>

<style>
    .tabs {
        width: 100%;
        max-width: 400px;
        margin: 20px auto;
        text-align: center;
    }

    .tabs input {
        display: none;
    }

    .tabs label {
        display: inline-block;
        padding: 10px 20px;
        cursor: pointer;
        background: #ddd;
        margin: 0;
        border-radius: 5px 5px 0 0;
    }

    .tabs label:hover {
        background: #bbb;
    }

    .tab-content {
        display: none;
        background: #eee;
        padding: 15px;
        border-radius: 0 0 5px 5px;
    }

    #tab1:checked~#content1,
    #tab2:checked~#content2,
    #tab3:checked~#content3 {
        display: block;
    }
</style>
```

### `Table-Data`
```HTML
<input type="text" id="search" placeholder="Search...">
<table id="dataTable">
    <thead>
        <tr>
            <th onclick="sortTable(0)">Name ⬍</th>
            <th onclick="sortTable(1)">Age ⬍</th>
            <th onclick="sortTable(2)">Country ⬍</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>28</td>
            <td>USA</td>
        </tr>
        <tr>
            <td>Alice</td>
            <td>24</td>
            <td>UK</td>
        </tr>
        <tr>
            <td>Bob</td>
            <td>30</td>
            <td>Canada</td>
        </tr>
    </tbody>
</table>

<script>
    document.getElementById("search").addEventListener("input", function () {
        let filter = this.value.toUpperCase();
        let rows = document.querySelectorAll("#dataTable tbody tr");

        rows.forEach(row => {
            row.style.display = row.textContent.toUpperCase().includes(filter) ? "" : "none";
        });
    });

    function sortTable(n) {
        let table = document.getElementById("dataTable");
        let rows = Array.from(table.rows).slice(1);
        let asc = table.getAttribute("data-sort") === "asc";

        rows.sort((rowA, rowB) => {
            let cellA = rowA.cells[n].textContent;
            let cellB = rowB.cells[n].textContent;
            return asc ? cellA.localeCompare(cellB) : cellB.localeCompare(cellA);
        });

        table.setAttribute("data-sort", asc ? "desc" : "asc");
        rows.forEach(row => table.appendChild(row));
    }
</script>

<style>
    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 10px;
    }

    th,
    td {
        padding: 10px;
        border: 1px solid #ddd;
        text-align: left;
    }

    th {
        background: #f4f4f4;
        cursor: pointer;
    }

    th:hover {
        background: #ddd;
    }

    input {
        padding: 8px;
        width: 100%;
        margin-bottom: 10px;
    }
</style>
```

### `Table-Pricing`
```HTML
<div class="pricing-table">
    <div class="plan">
        <h3>Basic</h3>
        <p>$10/month</p>
        <button>Select</button>
    </div>
    <div class="plan">
        <h3>Pro</h3>
        <p>$30/month</p>
        <button>Select</button>
    </div>
    <div class="plan">
        <h3>Enterprise</h3>
        <p>$50/month</p>
        <button>Select</button>
    </div>
</div>

<style>
    .pricing-table {
        display: flex;
        gap: 20px;
        text-align: center;
    }

    .plan {
        background: #f7f7f7;
        padding: 20px;
        border-radius: 8px;
        transition: 0.3s;
    }

    .plan:hover {
        transform: scale(1.05);
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    button {
        background: #ff9800;
        color: white;
        border: none;
        padding: 10px 15px;
        cursor: pointer;
        border-radius: 5px;
    }
</style>
```

### `Testionial-Slider`
```HTML
<div class="testimonial">
    <p>"This is an amazing service!"</p>
    <h4>- John Doe</h4>
</div>

<script>
    const testimonials = [
        '"This is an amazing service!" - John Doe',
        '"I love using this product!" - Jane Smith',
        '"Highly recommend to everyone!" - Alice Brown',
    ];

    let i = 0;
    function changeTestimonial() {
        document.querySelector(".testimonial p").innerText = testimonials[i].split(" - ")[0];
        document.querySelector(".testimonial h4").innerText = `- ${testimonials[i].split(" - ")[1]}`;
        i = (i + 1) % testimonials.length;
    }

    setInterval(changeTestimonial, 3000);
</script>

<style>
    .testimonial {
        width: 300px;
        text-align: center;
        padding: 20px;
        border: 2px solid #ddd;
        border-radius: 10px;
    }
</style>
```

### `Toast`
```HTML
<button onclick="showToast()">Show Notification</button>

<div class="toast">✔️ Success! Your action was completed.</div>

<style>
    .toast {
        position: fixed;
        bottom: -50px;
        left: 50%;
        transform: translateX(-50%);
        background: #4caf50;
        color: white;
        padding: 10px 20px;
        border-radius: 5px;
        transition: 0.3s;
    }

    .toast.show {
        bottom: 20px;
    }
</style>

<script>
    function showToast() {
        const toast = document.querySelector(".toast");
        toast.classList.add("show");
        setTimeout(() => toast.classList.remove("show"), 3000);
    }
</script>
```

### `Toggle-Dark-Mode`
```HTML
<label class="theme-toggle">
    <input type="checkbox" id="darkModeToggle">
    <span class="slider"></span>
</label>

<style>
    :root {
        --bg-color: white;
        --text-color: black;
    }

    body {
        background: var(--bg-color);
        color: var(--text-color);
        transition: 0.3s;
    }

    .theme-toggle {
        position: fixed;
        top: 20px;
        right: 20px;
        width: 50px;
        height: 25px;
    }

    .theme-toggle input {
        display: none;
    }

    .slider {
        position: absolute;
        width: 100%;
        height: 100%;
        background: #ddd;
        border-radius: 25px;
        transition: 0.3s;
    }

    .slider::before {
        content: "";
        position: absolute;
        width: 20px;
        height: 20px;
        background: white;
        border-radius: 50%;
        top: 50%;
        left: 4px;
        transform: translateY(-50%);
        transition: 0.3s;
    }

    .theme-toggle input:checked+.slider {
        background: black;
    }

    .theme-toggle input:checked+.slider::before {
        transform: translate(25px, -50%);
        background: yellow;
    }

    .theme-toggle input:checked~body {
        --bg-color: black;
        --text-color: white;
    }
</style>
```

### `Tooltip`
```HTML
<button class="tooltip-btn">Hover Me</button>
<div class="tooltip">This is a tooltip message!</div>

<style>
    .tooltip {
        position: absolute;
        background: #222;
        color: white;
        padding: 6px 12px;
        border-radius: 5px;
        font-size: 14px;
        visibility: hidden;
        opacity: 0;
        transition: 0.3s;
    }

    .tooltip-btn:hover+.tooltip {
        visibility: visible;
        opacity: 1;
        transform: translateY(-5px);
    }
</style>
```
