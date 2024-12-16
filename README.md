<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>fashionfactorsofficial.pk</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
        }
        .banner {
            width: 100%;
            max-width: 90%; /* Sets the maximum width to 90% of the container */
            max-height: 300px; /* Restricts the height to 300px */
            height: auto; /* Maintains the aspect ratio */
            object-fit: contain; /* Ensures the image remains contained within the box */
            display: block;
            margin: 0 auto; /* Centers the image */
        }
        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h2 {
            text-align: center;
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .error {
            color: red;
            font-size: 0.9em;
            margin-bottom: 15px;
            display: none;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #25d366;
            color: #fff;
            font-size: 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #128c7e;
        }
    </style>
</head>
<body>

<!-- Banner Section with Your Image URL -->
<img class="banner" src="file:///C:/Users/CDC/Downloads/WhatsApp%20Image%202024-11-23%20at%206.26.32%20AM.jpeg" alt="Banner Image">

<!-- Page Heading -->
<h1 style="text-align: center; font-size: 32px; margin-top: 20px;">fashionfactorsofficial.pk</h1>

<div class="container">
    <h2>Shipping Address Form</h2>
    <form id="shippingForm">
        <label for="name">Full Name</label>
        <input type="text" id="name" name="name" required>
        <p class="error" id="nameError">Full Name is required.</p>

        <label for="address">Shipping Address</label>
        <textarea id="address" name="address" rows="4" required></textarea>
        <p class="error" id="addressError">Shipping Address is required.</p>

        <label for="phone">Phone / WhatsApp Number</label>
        <input type="text" id="phone" name="phone" required>
        <p class="error" id="phoneError">Enter a valid phone number (digits only, 10-15 characters).</p>

        <button type="button" onclick="sendToWhatsApp()">Send to WhatsApp</button>
    </form>
</div>

<script>
    function validateForm() {
        let isValid = true;

        // Clear previous errors
        document.querySelectorAll('.error').forEach(error => error.style.display = 'none');

        // Validate Full Name
        const name = document.getElementById("name");
        if (!name.value.trim()) {
            document.getElementById("nameError").style.display = "block";
            name.focus();
            isValid = false;
        }

        // Validate Shipping Address
        const address = document.getElementById("address");
        if (!address.value.trim()) {
            document.getElementById("addressError").style.display = "block";
            if (isValid) address.focus();
            isValid = false;
        }

        // Validate Phone Number
        const phone = document.getElementById("phone");
        const phonePattern = /^[0-9]{10,15}$/;
        if (!phonePattern.test(phone.value)) {
            document.getElementById("phoneError").style.display = "block";
            if (isValid) phone.focus();
            isValid = false;
        }

        return isValid;
    }

    function sendToWhatsApp() {
        if (!validateForm()) return;

        const name = document.getElementById("name").value.trim();
        const address = document.getElementById("address").value.trim();
        const phone = document.getElementById("phone").value.trim();

        const targetNumber = "03296106987";
        const message = encodeURIComponent(`Shipping Info: \nName: ${name} \nAddress: ${address} \nPhone: ${phone}`);
        const whatsappUrl = `https://wa.me/${targetNumber}?text=${message}`;
        window.open(whatsappUrl, '_blank');
    }
</script>

</body>
</html>
