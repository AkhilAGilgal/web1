<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML5 Form Practice</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8; 
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        .form-container {
            background-color: #ffffff;
            padding: 32px;
            border-radius: 12px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            max-width: 700px;
            width: 100%;
            border: 1px solid #e2e8f0; 
        }
        .form-group {
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #4a5568; 
        }
        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="number"],
        input[type="date"],
        input[type="time"],
        input[type="url"],
        input[type="tel"],
        input[type="search"],
        select,
        textarea {
            width: 100%;
            padding: 12px 16px;
            border: 1px solid #cbd5e0; 
            border-radius: 8px;
            font-size: 16px;
            color: #2d3748; 
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
            box-sizing: border-box; 
        }
        input[type="text"]:focus,
        input[type="email"]:focus,
        input[type="password"]:focus,
        input[type="number"]:focus,
        input[type="date"]:focus,
        input[type="time"]:focus,
        input[type="url"]:focus,
        input[type="tel"]:focus,
        input[type="search"]:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: #6366f1; 
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.2); 
        }
        input[type="range"] {
            width: 100%;
            -webkit-appearance: none;
            appearance: none;
            background: transparent; 
        }
        input[type="range"]::-webkit-slider-runnable-track {
            height: 8px;
            background: #e2e8f0;
            border-radius: 4px;
        }
        input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            height: 20px;
            width: 20px;
            border-radius: 50%;
            background: #6366f1;
            cursor: pointer;
            margin-top: -6px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
        }
        input[type="range"]::-moz-range-track {
            height: 8px;
            background: #e2e8f0;
            border-radius: 4px;
        }
        input[type="range"]::-moz-range-thumb {
            height: 20px;
            width: 20px;
            border-radius: 50%;
            background: #6366f1;
            cursor: pointer;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
        }
        input[type="color"] {
            width: 80px; 
            height: 40px;
            padding: 4px;
            border-radius: 8px;
            border: 1px solid #cbd5e0;
        }
        .error-message {
            color: #ef4444; 
            font-size: 14px;
            margin-top: 4px;
            display: none; 
        }
        input:invalid:not(:placeholder-shown) {
            border-color: #ef4444; 
        }
        input:invalid:not(:placeholder-shown) + .error-message {
            display: block; 
        }
        .success-message {
            color: #22c55e; 
            font-size: 16px;
            margin-top: 15px;
            text-align: center;
            font-weight: 600;
        }
        .flex-row-wrap {
            display: flex;
            flex-wrap: wrap;
            gap: 20px; 
        }
        .flex-row-wrap > div {
            flex: 1 1 calc(50% - 10px); 
            min-width: 280px; 
        }
        @media (max-width: 640px) {
            .flex-row-wrap > div {
                flex: 1 1 100%; 
            }
        }
        .radio-group, .checkbox-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .radio-option, .checkbox-option {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        input[type="radio"], input[type="checkbox"] {
            width: auto; 
            height: auto; 
            margin: 0; 
            transform: scale(1.2); 
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1 class="text-3xl font-bold text-center text-gray-800 mb-8">Registration Form</h1>
        <form id="registrationForm" class="space-y-6">
            <fieldset class="border border-gray-200 p-6 rounded-lg shadow-sm">
                <legend class="text-lg font-semibold text-gray-700 px-2">Personal Information</legend>
               <div class="flex-row-wrap">
                    <div class="form-group">
                        <label for="fullName">Full Name:</label>
                        <input type="text" id="fullName" name="fullName" placeholder="John Doe" required
                               pattern="^[A-Za-z\s]{3,}$" title="Full name must contain only letters and spaces, minimum 3 characters.">
                        <span class="error-message">Please enter your full name (letters and spaces only, min 3 characters).</span>
                    </div>
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email" placeholder="john.doe@example.com" required>
                        <span class="error-message">Please enter a valid email address.</span>
                    </div>
                </div>
                <div class="flex-row-wrap">
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password" id="password" name="password" placeholder="********" required
                               pattern="^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$"
                               title="Password must be at least 8 characters long, contain at least one uppercase letter, one lowercase letter, one number, and one special character.">
                        <span class="error-message">Password must be 8+ chars, with uppercase, lowercase, number, and special char.</span>
                    </div>
                    <div class="form-group">
                        <label for="confirmPassword">Confirm Password:</label>
                        <input type="password" id="confirmPassword" name="confirmPassword" placeholder="********" required>
                        <span class="error-message" id="passwordMatchError">Passwords do not match.</span>
                    </div>
                </div>
                <div class="flex-row-wrap">
                    <div class="form-group">
                        <label for="dob">Date of Birth:</label>
                        <input type="date" id="dob" name="dob" required min="1900-01-01" max="2007-12-31">
                        <span class="error-message">Please enter a valid date of birth (you must be at least 18).</span>
                    </div>
                    <div class="form-group">
                        <label for="apptTime">Preferred Contact Time:</label>
                        <input type="time" id="apptTime" name="apptTime" min="09:00" max="17:00" required>
                        <span class="error-message">Please select a time between 9 AM and 5 PM.</span>
                    </div>
                </div>
                <div class="form-group">
                    <label for="age">Age (18-99): <span id="ageValue" class="font-normal text-gray-600">50</span></label>
                    <input type="range" id="age" name="age" min="18" max="99" value="50" step="1" required>
                </div>
                <div class="form-group">
                    <label for="favColor">Favorite Color:</label>
                    <input type="color" id="favColor" name="favColor" value="#6366f1">
                </div>
            </fieldset>
            <fieldset class="border border-gray-200 p-6 rounded-lg shadow-sm">
                <legend class="text-lg font-semibold text-gray-700 px-2">Contact & Preferences</legend>
                <div class="flex-row-wrap">
                    <div class="form-group">
                        <label for="website">Personal Website:</label>
                        <input type="url" id="website" name="website" placeholder="https://www.example.com"
                               pattern="https?://.+" title="Please enter a valid URL starting with http:// or https://">
                        <span class="error-message">Please enter a valid website URL.</span>
                    </div>
                    <div class="form-group">
                        <label for="phone">Phone Number:</label>
                        <input type="tel" id="phone" name="phone" placeholder="123-456-7890"
                               pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" title="Format: 123-456-7890">
                        <span class="error-message">Please enter a valid phone number (e.g., 123-456-7890).</span>
                    </div>
                </div>
                <div class="form-group">
                    <label for="searchQuery">Search for something:</label>
                    <input type="search" id="searchQuery" name="searchQuery" placeholder="e.g., HTML forms">
               </div>
               <div class="form-group">
                    <label for="profilePicture">Upload Profile Picture:</label>
                    <input type="file" id="profilePicture" name="profilePicture" accept="image/*">
                </div>
                <div class="form-group">
                    <label>Gender:</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" id="genderMale" name="gender" value="male" required>
                            <label for="genderMale">Male</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" id="genderFemale" name="gender" value="female">
                            <label for="genderFemale">Female</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" id="genderOther" name="gender" value="other">
                            <label for="genderOther">Other</label>
                        </div>
                    </div>
                    <span class="error-message">Please select your gender.</span>
                </div>
                <div class="form-group">
                    <label>Interests:</label>
                    <div class="checkbox-group">
                        <div class="checkbox-option">
                            <input type="checkbox" id="interestCoding" name="interests" value="coding">
                            <label for="interestCoding">Coding</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="interestDesign" name="interests" value="design">
                            <label for="interestDesign">Design</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="interestReading" name="interests" value="reading">
                            <label for="interestReading">Reading</label>
                        </div>
                        <div class="checkbox-option">
                            <input type="checkbox" id="interestSports" name="interests" value="sports">
                            <label for="interestSports">Sports</label>
                        </div>
                    </div>
                </div>
                <div class="form-group">
                    <label for="country">Country:</label>
                    <select id="country" name="country" required>
                        <option value="">--Please choose an option--</option>
                        <option value="usa">United States</option>
                        <option value="canada">Canada</option>
                        <option value="uk">United Kingdom</option>
                        <option value="india">India</option>
                        <option value="australia">Australia</option>
                        <option value="germany">Germany</option>
                    </select>
                    <span class="error-message">Please select your country.</span>
                </div>
                <div class="form-group">
                    <label for="comments">Comments:</label>
                    <textarea id="comments" name="comments" rows="4" placeholder="Any additional comments..."
                             maxlength="500"></textarea>
                </div>
            </fieldset>
            <div class="form-group text-center">
                <button type="submit"
                        class="bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 px-8 rounded-lg
                               shadow-lg transition duration-300 ease-in-out transform hover:scale-105 focus:outline-none focus:ring-4 focus:ring-indigo-500 focus:ring-opacity-50">
                    Submit Form
                </button>
            </div>
            <div id="formStatus" class="success-message" style="display: none;"></div>
        </form>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const form = document.getElementById('registrationForm');
            const passwordInput = document.getElementById('password');
            const confirmPasswordInput = document.getElementById('confirmPassword');
            const passwordMatchError = document.getElementById('passwordMatchError');
            const ageInput = document.getElementById('age');
            const ageValueSpan = document.getElementById('ageValue');
            const formStatus = document.getElementById('formStatus');
            ageInput.addEventListener('input', function() {
                ageValueSpan.textContent = this.value;
            });
            function validatePasswordMatch() {
                if (passwordInput.value !== confirmPasswordInput.value) {
                    confirmPasswordInput.setCustomValidity("Passwords do not match.");
                    passwordMatchError.style.display = 'block';
                } else {
                    confirmPasswordInput.setCustomValidity(""); 
                    passwordMatchError.style.display = 'none';
                }
            }
            passwordInput.addEventListener('input', validatePasswordMatch);
            confirmPasswordInput.addEventListener('input', validatePasswordMatch);
            form.querySelectorAll('input, select, textarea').forEach(input => {
                input.addEventListener('invalid', function() {
                    const errorMessageSpan = this.nextElementSibling;
                    if (errorMessageSpan && errorMessageSpan.classList.contains('error-message')) {
                        errorMessageSpan.style.display = 'block';
                    }
                });
                input.addEventListener('input', function() {
                    const errorMessageSpan = this.nextElementSibling;
                    if (errorMessageSpan && errorMessageSpan.classList.contains('error-message')) {
                        if (this.validity.valid) {
                            errorMessageSpan.style.display = 'none';
                        }
                    }
                });
            });
            form.addEventListener('submit', function(event) {
                event.preventDefault(); 
                validatePasswordMatch();
                if (form.checkValidity()) {      
                    console.log('Form is valid! Submitting data...');
                    const formData = new FormData(form);
                    const data = {};
                    for (let [key, value] of formData.entries()) {
                               if (key === 'interests') {
                            if (!data[key]) {
                                data[key] = [];
                            }
                            data[key].push(value);
                        } else {
                            data[key] = value;
                        }
                    }
                    console.log('Form Data:', data);
                    formStatus.textContent = 'Form submitted successfully!';
                    formStatus.style.display = 'block';
                    formStatus.style.color = '#22c55e'; 
                } else {
                         form.querySelectorAll('input:invalid, select:invalid, textarea:invalid').forEach(invalidInput => {
                        const errorMessageSpan = invalidInput.nextElementSibling;
                        if (errorMessageSpan && errorMessageSpan.classList.contains('error-message')) {
                            errorMessageSpan.style.display = 'block';
                        }
                    });
                    formStatus.textContent = 'Please correct the errors in the form.';
                    formStatus.style.display = 'block';
                    formStatus.style.color = '#ef4444'; 
                }
            });
        });
    </script>
</body>
</html>
