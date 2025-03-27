# feb-2025-avasjcript-events-and-basic-interactivity

document.addEventListener("DOMContentLoaded", () => {
    // Form validation
    document.getElementById("demoForm").addEventListener("submit", function(event) {
        event.preventDefault();
        
        let name = document.getElementById("name").value.trim();
        let email = document.getElementById("email").value.trim();
        let message = document.getElementById("formMessage");

        if (name === "" || email === "") {
            message.textContent = "All fields are required!";
            message.style.color = "red";
        } else if (!email.includes("@")) {
            message.textContent = "Enter a valid email address!";
            message.style.color = "red";
        } else {
            message.textContent = "Form submitted successfully!";
            message.style.color = "green";
        }
    });

    // Toggle visibility of a message
    document.getElementById("toggleButton").addEventListener("click", () => {
        let message = document.getElementById("hiddenMessage");
        message.classList.toggle("hidden");
    });

    // Change background color randomly
    document.getElementById("colorButton").addEventListener("click", () => {
        let colors = ["#ffcccb", "#d4edda", "#cce5ff", "#f8d7da", "#fff3cd"];
        document.body.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
    });
});