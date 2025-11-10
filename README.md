<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Warranty Card Submission</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen p-4">
    <div class="bg-white p-8 rounded-2xl shadow-xl w-full max-w-2xl border border-gray-200">
        <h1 class="text-3xl font-bold text-center text-gray-800 mb-2">Warranty Card</h1>
        <p class="text-center text-gray-500 mb-6">Fill out the form below to submit your warranty card.
            <br>
        </p>
        
        <form id="parts-form" class="space-y-4">

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
                <label for="occupancy" class="block text-sm font-medium text-gray-700">Occupancy</label>
                <select id="occupancy" name="occupancy" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select occupancy status</option>
                    <option value="Homeowner">Homeowner</option>
                    <option value="Renter">Renter</option>
                </select>
            </div>
            
            <fieldset class="border p-4 rounded-lg space-y-4">
                <legend class="text-sm font-semibold text-gray-700 px-2">Homeowner Details (Primary)</legend>

                <div class="space-y-2">
                    <label for="homeowner-name" class="block text-sm font-medium text-gray-700">Homeowner Name</label>
                    <input type="text" id="homeowner-name" name="homeowner-name" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="user-phone" class="block text-sm font-medium text-gray-700">Homeowner Phone Number</label> <input type="tel" id="user-phone" name="homeowner-phone-1" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="company-email" class="block text-sm font-medium text-gray-700">Homeowner Email</label> <input type="email" id="company-email" name="homeowner-email-1" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>
            </fieldset>

            <fieldset class="border p-4 rounded-lg space-y-4">
                <legend class="text-sm font-semibold text-gray-700 px-2">Homeowner Details (Secondary - Optional)</legend>

                <div class="space-y-2">
                    <label for="homeowner-name-2" class="block text-sm font-medium text-gray-700">Homeowner Name #2</label>
                    <input type="text" id="homeowner-name-2" name="homeowner-name-2" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="homeowner-phone-2" class="block text-sm font-medium text-gray-700">Homeowner Phone Number #2</label>
                    <input type="tel" id="homeowner-phone-2" name="homeowner-phone-2" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="homeowner-email-2" class="block text-sm font-medium text-gray-700">Homeowner Email #2</label>
                    <input type="email" id="homeowner-email-2" name="homeowner-email-2" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>
            </fieldset>


            <fieldset class="border p-4 rounded-lg space-y-4">
                <legend class="text-sm font-semibold text-gray-700 px-2">Property Address</legend>
                
                <div class="space-y-2">
                    <label for="street-address" class="block text-sm font-medium text-gray-700">Street Address</label>
                    <input type="text" id="street-address" name="street-address" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>
                
                <div class="flex space-x-4">
                    <div class="w-1/2 space-y-2">
                        <label for="state-code" class="block text-sm font-medium text-gray-700">State</label>
                        <select id="state-code" name="state-code" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                            </select>
                    </div>
                    <div class="w-1/2 space-y-2">
                        <label for="zip-code" class="block text-sm font-medium text-gray-700">ZIP Code</label>
                        <input type="text" id="zip-code" name="zip-code" pattern="[0-9]{5}" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    </div>
                </div>
            </fieldset>
            <div class="space-y-2">
                <label for="individual-name" class="block text-sm font-medium text-gray-700">Individual Submitting Warranty Card</label>
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
            
            <div class="mt-6">
                <button type="submit" id="submit-btn" class="w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold text-lg transition duration-150 ease-in-out shadow-lg">
                    Submit Warranty Card
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

            // US State Codes (verified 50 states)
            const US_STATES = [
                'AL', 'AK', 'AZ', 'AR', 'CA', 'CO', 'CT', 'DE', 'FL', 'GA', 'HI', 'ID', 'IL', 'IN', 'IA', 'KS', 
                'KY', 'LA', 'ME', 'MD', 'MA', 'MI', 'MN', 'MS', 'MO', 'MT', 'NE', 'NV', 'NH', 'NJ', 'NM', 'NY', 
                'NC', 'ND', 'OH', 'OK', 'OR', 'PA', 'RI', 'SC', 'SD', 'TN', 'TX', 'UT', 'VT', 'VA', 'WA', 'WV', 
                'WI', 'WY'
            ];

            // DOM elements
            const form = document.getElementById('parts-form');
            const communitySelect = document.getElementById('community-select');
            const otherCommunityDiv = document.getElementById('other-community-div');
            const otherCommunityInput = document.getElementById('other-community');
            const statusDiv = document.getElementById('status-message');
            const submitBtn = document.getElementById('submit-btn');
            const formMainContent = document.querySelector('form');
            const individualNameSelect = document.getElementById('individual-name');
            const homeownerPhone1Input = document.getElementById('user-phone'); // RENAMED REFERENCE
            const homeownerEmail1Input = document.getElementById('company-email'); // RENAMED REFERENCE
            const stateCodeSelect = document.getElementById('state-code');

            // Function to populate state dropdown
            function populateStates() {
                let options = '<option value="" disabled selected>Select state</option>';
                US_STATES.forEach(state => {
                    options += `<option value="${state}">${state}</option>`;
                });
                stateCodeSelect.innerHTML = options;
            }

            // Function to reset the entire form and show it again
            function resetForm() {
                form.reset();
                statusDiv.classList.add('hidden');
                otherCommunityDiv.classList.add('hidden');
                otherCommunityInput.required = false;
                otherCommunityInput.name = 'unused';
                formMainContent.style.display = 'block';
            }

            // Initialize: populate states
            populateStates(); 

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

            // --- CONTACT LOGIC: Auto-fill now targets HOMEOWNER #1 fields ---
            const individualContacts = {
                'Carl Thomas': { phone: '817-902-9543', email: '345hsllc@gmail.com' },
                'Jerry Velasquez': { phone: '903-715-3217', email: 'jerryleevmhs@outlook.com' },
                'Ray Howell': { phone: '817-902-5404', email: 'big.eagle77@yahoo.com' },
                'Shawn Thomas': { phone: '817-995-1818', email: 'shawn.thomas@peakmhc.com' },
                'Jason Cappers': { phone: '318-540-9909', email: 'jason.cappers@peakenterprises.com' },
                'Jeff Braswell': { phone: '940-594-2891', email: 'jeff.braswell@peakenterprises.com' },
                'Chris Brown': { phone: '512-777-0351', email: 'chris.brown@peakenterprises.com' }
            };

            // Event listener to auto-populate Homeowner Phone #1 and Email #1 based on the Submitting INDIVIDUAL
            individualNameSelect.addEventListener('change', (event) => {
                const selectedIndividual = event.target.value;
                const contacts = individualContacts[selectedIndividual];
                
                if (contacts) {
                    homeownerPhone1Input.value = contacts.phone;
                    homeownerEmail1Input.value = contacts.email;
                } else {
                    homeownerPhone1Input.value = '';
                    homeownerEmail1Input.value = '';
                }
            });
            // --- END CONTACT LOGIC ---

            emailjs.init(USER_ID);

            document.getElementById('parts-form').addEventListener('submit', function(event) {
                event.preventDefault();
                
                // Get email from the primary homeowner's email field
                const primaryHomeownerEmail = form.elements['homeowner-email-1'].value.trim();
                
                if (!primaryHomeownerEmail) {
                    statusDiv.classList.remove('hidden', 'bg-blue-100', 'text-blue-800', 'bg-green-100', 'text-green-800');
                    statusDiv.classList.add('bg-red-100', 'text-red-800');
                    statusDiv.innerHTML = '<strong>Error!</strong> Please provide a valid Homeowner Email address.';
                    formMainContent.style.display = 'block';
                    return; 
                }

                // Show loading state and hide the form
                formMainContent.style.display = 'none';
                statusDiv.classList.remove('hidden', 'bg-green-100', 'text-green-800', 'bg-red-100', 'text-red-800');
                statusDiv.classList.add('bg-blue-100', 'text-blue-800');
                statusDiv.innerHTML = 'Sending request...';
                
                submitBtn.disabled = true;
                
                const orderRequestParams = {
                    // Home Info
                    'home-manufacturer': form.elements['home-manufacturer'].value,
                    'community': communitySelect.value === 'Other' ? otherCommunityInput.value : communitySelect.value, 
                    'lot-number': form.elements['lot-number'].value,
                    'serial-number': form.elements['serial-number'].value,
                    'occupancy': form.elements['occupancy'].value,

                    // Homeowner #1 Details
                    'homeowner-name-1': form.elements['homeowner-name'].value, // Renamed key to clarify primary
                    'homeowner-phone-1': form.elements['homeowner-phone-1'].value,
                    'homeowner-email-1': primaryHomeownerEmail,

                    // Homeowner #2 Details (Optional)
                    'homeowner-name-2': form.elements['homeowner-name-2'].value || 'N/A', // Send N/A if blank
                    'homeowner-phone-2': form.elements['homeowner-phone-2'].value || 'N/A',
                    'homeowner-email-2': form.elements['homeowner-email-2'].value || 'N/A',
                    
                    // Property Address
                    'street-address': form.elements['street-address'].value,
                    'state-code': form.elements['state-code'].value,
                    'zip-code': form.elements['zip-code'].value,

                    // Submitter Info
                    'individual-name': form.elements['individual-name'].value,
                };
                
                const confirmationParams = {
                    'to_email': primaryHomeownerEmail, // Send confirmation to Homeowner #1
                    
                    // All other parameters remain the same for confirmation email content
                    ...orderRequestParams
                };

                // First, send the Warranty Card submission
                emailjs.send(SERVICE_ID, TEMPLATE_ID, orderRequestParams)
                    .then(function() {
                        // On success, send the confirmation email to the primary homeowner
                        return emailjs.send(SERVICE_ID, CONFIRMATION_TEMPLATE_ID, confirmationParams);
                    })
                    .then(function() {
                        // Show success message with a Continue button after both emails are sent
                        statusDiv.classList.remove('bg-blue-100', 'text-blue-800');
                        statusDiv.classList.add('bg-green-100', 'text-green-800');
                        statusDiv.innerHTML = '<strong>Success!</strong> Your Warranty Card has been sent, and a confirmation email has been sent to the primary homeowner\'s inbox. <br><br> <button id="continue-btn" class="py-2 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold transition duration-150 ease-in-out">Continue</button>';
                        
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
