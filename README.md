<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manufactured Home Parts Order</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .part-entry:not(:first-child) {
            margin-top: 1.5rem; /* Add spacing between multiple parts */
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen p-4">
    <div class="bg-white p-8 rounded-2xl shadow-xl w-full max-w-2xl border border-gray-200">
        <h1 class="text-3xl font-bold text-center text-gray-800 mb-2">Parts Order Request</h1>
        <p class="text-center text-gray-500 mb-6">Fill out the form below to order parts for your home.
            <br>
        </p>
        
        <form id="parts-form" class="space-y-4">
            <div class="space-y-2">
                <label for="user-name" class="block text-sm font-medium text-gray-700">Company Name</label>
                <select id="user-name" name="user-name" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select a company</option>
                    <option value="345 Handyman Services">345 Handyman Services</option>
                    <option value="G-Velasquez MHS">G-Velasquez MHS</option>
                    <option value="Hand in Hand Carpentry">Hand in Hand Carpentry</option>
                    <option value="Peak Enterprises">Peak Enterprises</option>
                </select>
            </div>
            <div class="space-y-2">
                <label for="individual-name" class="block text-sm font-medium text-gray-700">Individual requesting parts</label>
                <!-- UPDATED TO DROPDOWN -->
                <select id="individual-name" name="individual-name" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select individual</option>
                    <option value="Carl Thomas">Carl Thomas</option>
                    <option value="Chris Brown">Chris Brown</option>
                    <option value="Jason Cappers">Jason Cappers</option>
                    <option value="Jeff Braswell">Jeff Braswell</option>
                    <option value="Jerry Velasquez">Jerry Velasquez</option>
                    <option value="Ray Howell">Ray Howell</option>
                    <option value="Shawn Thomas">Shawn Thomas</option>
                </select>
            </div>
            <div class="space-y-2">
                <label for="user-phone" class="block text-sm font-medium text-gray-700">Phone Number</label>
                <input type="tel" id="user-phone" name="user-phone" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            <div class="space-y-2">
                <label for="company-email" class="block text-sm font-medium text-gray-700">Company Email</label>
                <input type="email" id="company-email" name="company-email" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            
            <div class="space-y-2">
                <label for="home-address" class="block text-sm font-medium text-gray-700">Community</label>
                <select id="community-select" name="community" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select your community</option>
                    <option value="Rancho Serenidad">Rancho Serenidad</option>
                    <option value="Villas De Mariposa">Villas De Mariposa</option>
                    <option value="Brazos Point">Brazos Point</option>
                    <option value="Solena">Solena</option>
                    <option value="Other">Other (Please specify)</option>
                </select>
            </div>
            
            <div id="other-community-div" class="space-y-2 hidden">
                <label for="other-community" class="block text-sm font-medium text-gray-700">Specify Community</label>
                <input type="text" id="other-community" name="home-address" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            <div class="space-y-2">
                <label for="lot-number" class="block text-sm font-medium text-gray-700">Lot Number</label>
                <input type="text" id="lot-number" name="lot-number" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            <div class="space-y-2">
                <label for="serial-number" class="block text-sm font-medium text-gray-700">Serial Number</label>
                <input type="text" id="serial-number" name="serial-number" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            
            <div class="space-y-2">
                <label for="home-manufacturer" class="block text-sm font-medium text-gray-700">Home Manufacturer</label>
                <select id="home-manufacturer" name="home-manufacturer" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select a manufacturer</option>
                    <option value="CAVCO/Fleetwood">CAVCO/Fleetwood</option>
                    <option value="Champion Homes">Champion Homes</option>
                    <option value="Clayton Athens">Clayton Athens</option>
                    <option value="Clayton Bonham">Clayton Bonham</option>
                    <option value="Clayton Southern Energy">Clayton Southern Energy</option>
                    <option value="Clayton Sulphur Springs">Clayton Sulphur Springs</option>
                    <option value="Clayton Waco1">Clayton Waco1</option>
                    <option value="Jessup">Jessup</option>
                    <option value="New Vision">New Vision</option>
                    <option value="Oak Creek">Oak Creek</option>
                    <option value="RGN">RGN</option>
                </select>
            </div>
            
            <div id="parts-container" class="space-y-6 mt-6">
            </div>
            
            <div class="flex space-x-4 pt-4">
                <button type="button" id="add-part-btn" class="w-1/2 py-2 px-4 bg-gray-200 hover:bg-gray-300 rounded-full text-gray-700 font-semibold text-sm transition duration-150 ease-in-out">
                    Add Another Part
                </button>
                <button type="button" id="remove-part-btn" disabled class="w-1/2 py-2 px-4 bg-gray-200 opacity-50 cursor-not-allowed rounded-full text-gray-700 font-semibold text-sm transition duration-150 ease-in-out">
                    Remove Last Part
                </button>
            </div>
            
            <div class="mt-6">
                <button type="submit" id="submit-btn" class="w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold text-lg transition duration-150 ease-in-out shadow-lg">
                    Submit Order
                </button>
            </div>
        </form>

        <div id="status-message" class="mt-6 p-4 rounded-lg text-center hidden"></div>
    </div>

    <script>
        (function() {
            // Your EmailJS User ID, Service ID, and Template ID.
            const USER_ID = 'bSgwpRuVeEky48mPe'; 
            const SERVICE_ID = 'service_7lbsq24';
            const TEMPLATE_ID = 'template_mumbvhg';
            const CONFIRMATION_TEMPLATE_ID = 'template_k6klnym';

            // DOM elements
            const form = document.getElementById('parts-form');
            const communitySelect = document.getElementById('community-select');
            const otherCommunityDiv = document.getElementById('other-community-div');
            const otherCommunityInput = document.getElementById('other-community');
            const statusDiv = document.getElementById('status-message');
            const submitBtn = document.getElementById('submit-btn');
            const removePartBtn = document.getElementById('remove-part-btn'); 
            const userNameSelect = document.getElementById('user-name');
            const individualNameSelect = document.getElementById('individual-name'); // New reference to the individual dropdown
            const userPhoneInput = document.getElementById('user-phone');
            const companyEmailInput = document.getElementById('company-email');
            const partsContainer = document.getElementById('parts-container');
            const addPartBtn = document.getElementById('add-part-btn');
            const formMainContent = document.querySelector('form');

            let partCounter = 0;

            // Define part locations
            const partLocations = [
                "Exterior", 
                "Primary Bedroom",
                "Primary Bathroom",
                "Bedroom #2",
                "Bedroom #3",
                "Bedroom #4",
                "Flex Space",
                "Hall",
                "Guest Bath",
                "Living Area",
                "Laundry Area",
                "Dining Area",
                "Kitchen",
                "Pantry",
                "Marriage Line"
            ];
            
            // Function to update the disabled state of the remove button
            function updateRemoveButtonState() {
                const parts = partsContainer.querySelectorAll('.part-entry');
                if (parts.length <= 1) {
                    removePartBtn.disabled = true;
                    removePartBtn.classList.add('opacity-50', 'cursor-not-allowed');
                } else {
                    removePartBtn.disabled = false;
                    removePartBtn.classList.remove('opacity-50', 'cursor-not-allowed');
                }
            }
            
            // Function to add a new part entry
            function addPartEntry() {
                partCounter++;
                const partDiv = document.createElement('div');
                partDiv.classList.add('part-entry', 'bg-gray-50', 'p-4', 'rounded-lg', 'border', 'border-gray-200', 'space-y-4');
                
                partDiv.innerHTML = `
                    <h3 class="font-semibold text-gray-700">Part #${partCounter}</h3>
                    
                    <div class="flex space-x-4">
                        <div class="w-1/3 space-y-2">
                            <label for="part-quantity-${partCounter}" class="block text-sm font-medium text-gray-700">Quantity</label>
                            <input type="number" id="part-quantity-${partCounter}" name="part-quantity-${partCounter}" min="1" value="1" required 
                                class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                        </div>
                        <div class="w-2/3 space-y-2">
                            <label for="part-location-${partCounter}" class="block text-sm font-medium text-gray-700">Part Location In Home</label>
                            <select id="part-location-${partCounter}" name="part-location-${partCounter}" required 
                                class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                                <option value="" disabled selected>Select location</option>
                                ${partLocations.map(location => `<option value="${location}">${location}</option>`).join('')}
                            </select>
                        </div>
                    </div>

                    <div class="space-y-2">
                        <label for="part-description-${partCounter}" class="block text-sm font-medium text-gray-700">Part Description / Details</label>
                        <textarea id="part-description-${partCounter}" name="part-description-${partCounter}" rows="2" required 
                            class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out"></textarea>
                    </div>

                    <div class="space-y-2">
                        <label for="part-reason-${partCounter}" class="block text-sm font-medium text-gray-700">Reason for Request</label>
                        <select id="part-reason-${partCounter}" name="part-reason-${partCounter}" required 
                            class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                            <option value="" disabled selected>Select reason</option>
                            <option value="Damaged">Damaged</option>
                            <option value="Missing from Ship Loose">Missing from Ship Loose</option>
                            <option value="Service">Service</option>
                        </select>
                    </div>
                `;
                partsContainer.appendChild(partDiv);
                updateRemoveButtonState();
            }

            // Function to remove the last part entry
            function removePartEntry() {
                const parts = partsContainer.querySelectorAll('.part-entry');
                if (parts.length > 1) {
                    const lastPart = parts[parts.length - 1];
                    partsContainer.removeChild(lastPart);
                    partCounter--;
                    updateRemoveButtonState();
                }
            }

            // Function to reset the entire form and show it again
            function resetForm() {
                form.reset();
                partsContainer.innerHTML = '';
                partCounter = 0;
                addPartEntry();
                statusDiv.classList.add('hidden');
                otherCommunityDiv.classList.add('hidden');
                otherCommunityInput.required = false;
                otherCommunityInput.name = 'unused';
                formMainContent.style.display = 'block';
                updateRemoveButtonState(); // Ensure the button is disabled after reset
            }

            // Initially add the first part entry
            addPartEntry();

            // Event listeners
            addPartBtn.addEventListener('click', addPartEntry);
            removePartBtn.addEventListener('click', removePartEntry);
            
            // --- NEW CONTACT LOGIC ---
            // 1. Contact information for each individual
            const individualContacts = {
                'Carl Thomas': { phone: '817-902-9543', email: '345hsllc@gmail.com' },
                'Jerry Velasquez': { phone: '903-715-3217', email: 'jerryleevmhs@outlook.com' },
                'Ray Howell': { phone: '817-902-5404', email: 'big.eagle77@yahoo.com' },
                'Shawn Thomas': { phone: '817-995-1818', email: 'shawn.thomas@peakmhc.com' }, // <-- UPDATED EMAIL
                'Jason Cappers': { phone: '318-540-9909', email: 'jason.cappers@peakenterprises.com' },
                'Jeff Braswell': { phone: '940-594-2891', email: 'jeff.braswell@peakenterprises.com' },
                'Chris Brown': { phone: '512-777-0351', email: 'chris.brown@peakenterprises.com' }
            };

            // 2. Event listener to auto-populate phone number and email based on the INDIVIDUAL
            individualNameSelect.addEventListener('change', (event) => {
                const selectedIndividual = event.target.value;
                const contacts = individualContacts[selectedIndividual];
                
                // Clear company contact info, as it is no longer used for auto-fill
                // We are now only auto-filling the individual's contact fields
                if (contacts) {
                    userPhoneInput.value = contacts.phone;
                    companyEmailInput.value = contacts.email;
                } else {
                    userPhoneInput.value = '';
                    companyEmailInput.value = '';
                }
            });
            // --- END NEW CONTACT LOGIC ---

            // Handle "Other" option in community dropdown
            communitySelect.addEventListener('change', (event) => {
                if (event.target.value === 'Other') {
                    otherCommunityDiv.classList.remove('hidden');
                    otherCommunityInput.required = true;
                    otherCommunityInput.name = 'home-address';
                } else {
                    otherCommunityDiv.classList.add('hidden');
                    otherCommunityInput.required = false;
                    otherCommunityInput.name = 'unused';
                }
            });

            emailjs.init(USER_ID);

            document.getElementById('parts-form').addEventListener('submit', function(event) {
                event.preventDefault();
                
                const companyEmail = form.elements['company-email'].value.trim();
                
                // New, more robust validation check
                if (!companyEmail) {
                    // Show validation error for email
                    statusDiv.classList.remove('hidden', 'bg-blue-100', 'text-blue-800', 'bg-green-100', 'text-green-800');
                    statusDiv.classList.add('bg-red-100', 'text-red-800');
                    statusDiv.innerHTML = '<strong>Error!</strong> Please provide a valid company email address.';
                    formMainContent.style.display = 'block';
                    return; // Stop the function from proceeding
                }

                // Show loading state and hide the form
                formMainContent.style.display = 'none';
                statusDiv.classList.remove('hidden', 'bg-green-100', 'text-green-800', 'bg-red-100', 'text-red-800');
                statusDiv.classList.add('bg-blue-100', 'text-blue-800');
                statusDiv.innerHTML = 'Sending request...';
                
                submitBtn.disabled = true;
                
                // Collect all part data and build the string
                const partDescriptions = document.querySelectorAll('[name^="part-description-"]');
                const partLocations = document.querySelectorAll('[name^="part-location-"]');
                const partQuantities = document.querySelectorAll('[name^="part-quantity-"]');
                const partReasons = document.querySelectorAll('[name^="part-reason-"]'); // NEW: Get reasons
                
                let partsString = '';
                for (let i = 0; i < partDescriptions.length; i++) {
                    partsString += `Part #${i + 1}:\n`;
                    partsString += `  Quantity: ${partQuantities[i].value}\n`;
                    partsString += `  Location: ${partLocations[i].value}\n`;
                    partsString += `  Reason: ${partReasons[i].value}\n`; // NEW: Include reason
                    partsString += `  Description: ${partDescriptions[i].value}\n\n`;
                }

                const orderRequestParams = {
                    'user-name': form.elements['user-name'].value,
                    'company-email': companyEmail,
                    'user-phone': form.elements['user-phone'].value,
                    'individual-name': form.elements['individual-name'].value,
                    'home-address': communitySelect.value === 'Other' ? otherCommunityInput.value : communitySelect.value,
                    'lot-number': form.elements['lot-number'].value,
                    'serial-number': form.elements['serial-number'].value,
                    'home-manufacturer': form.elements['home-manufacturer'].value,
                    'part-description': partsString,
                };
                
                const confirmationParams = {
                    'to_email': companyEmail,
                    'user-name': form.elements['user-name'].value,
                    'individual-name': form.elements['individual-name'].value,
                    'user-phone': form.elements['user-phone'].value,
                    'company-email': companyEmail,
                    'home-address': communitySelect.value === 'Other' ? otherCommunityInput.value : communitySelect.value,
                    'lot-number': form.elements['lot-number'].value,
                    'serial-number': form.elements['serial-number'].value,
                    'home-manufacturer': form.elements['home-manufacturer'].value,
                    'part-description': partsString,
                };

                // First, send the parts order request
                emailjs.send(SERVICE_ID, TEMPLATE_ID, orderRequestParams)
                    .then(function() {
                        // On success, send the confirmation email to the user
                        return emailjs.send(SERVICE_ID, CONFIRMATION_TEMPLATE_ID, confirmationParams);
                    })
                    .then(function() {
                        // Show success message with a Continue button after both emails are sent
                        statusDiv.classList.remove('bg-blue-100', 'text-blue-800');
                        statusDiv.classList.add('bg-green-100', 'text-green-800');
                        statusDiv.innerHTML = '<strong>Success!</strong> Your parts order has been sent, and a confirmation email has been sent to your inbox. <br><br> <button id="continue-btn" class="py-2 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold transition duration-150 ease-in-out">Continue</button>';
                        
                        // Add event listener to the newly created button
                        document.getElementById('continue-btn').addEventListener('click', resetForm);
                    }, function(error) {
                        // Handle failure of either email and show the form again
                        statusDiv.classList.remove('bg-blue-100', 'text-blue-800');
                        statusDiv.classList.add('bg-red-100', 'text-red-800');
                        statusDiv.innerHTML = `<strong>Failed!</strong> There was an error sending your request. Error: ${JSON.stringify(error)}`;
                        console.error('EmailJS Error:', error);
                        formMainContent.style.display = 'block';
                    })
                    .finally(() => {
                        submitBtn.disabled = false;
                    });
            });
        })();
    </script>
</body>
</html>
