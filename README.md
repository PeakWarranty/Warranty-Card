<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Warranty Card Creation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom styles for the hidden export template to match the image */
        #warranty-card-template {
            width: 800px; /* Fixed width for consistent output resolution */
            border-collapse: collapse;
            font-size: 14px;
            font-family: Arial, sans-serif;
        }
        #warranty-card-template th, #warranty-card-template td {
            border: 1px solid black;
            padding: 8px 12px;
            text-align: left;
            vertical-align: top;
        }
        #warranty-card-template th {
            background-color: #f0f0f0;
            font-weight: bold;
            width: 30%;
        }
        #warranty-card-template .data-cell {
            font-weight: bold;
            width: 70%;
        }
        #warranty-card-template .header-row td {
            text-align: center;
            font-weight: bold;
            background-color: #ddd;
        }
        /* Adjusted styles for template output */
        .manufacturer-name-large { 
            font-size: 1.25em; 
            font-weight: bold;
        }
        /* Simplified Purchaser/Phone layout for merging cells */
        .purchaser-name-cell {
            width: 25%; 
            border-right: none;
        }
        .purchaser-phone-cell {
            width: 25%;
        }
        .facility-header {
            text-align: center;
            font-weight: bold;
            background-color: #ddd;
        }
        .facility-label {
            width: 33.33%;
            text-align: center;
            font-weight: bold;
        }
        .facility-data {
            text-align: center;
            font-weight: normal;
        }
    </style>
</head>
<body class="bg-blue-900/5 flex items-center justify-center min-h-screen p-4"> <div class="bg-white p-8 rounded-2xl shadow-xl w-[95%] md:w-[85%] lg:w-[90%] border border-gray-200">
        <h1 class="text-3xl font-bold text-center text-gray-800 mb-2">Warranty Card Creation</h1>
        <p class="text-center text-gray-500 mb-6">Fill out the form below to create your JPEG Warranty Card.</p>
        
        <form id="parts-form" class="space-y-4">

            <div class="space-y-2">
                <label for="date-sold" class="block text-sm font-medium text-gray-700">Date of Sale</label>
                <input type="date" id="date-sold" name="date-sold" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>

            <div class="space-y-2">
                <label for="sold-by" class="block text-sm font-medium text-gray-700">Sold By (Retailer)</label>
                <select id="sold-by" name="sold-by" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select the selling retailer</option>
                    <option value="CRE-BUFFALO CREEK OWNER LLC">CRE-BUFFALO CREEK OWNER LLC</option>
                    <option value="CRE-MPC PRINCETON OWNER LLC">CRE-MPC PRINCETON OWNER LLC</option>
                    <option value="LMP DEER CREEKOWNER LLC">LMP DEER CREEKOWNER LLC</option>
                    <option value="PE BRAZOS POINT MHC LLC">PE BRAZOS POINT MHC LLC</option>
                </select>
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
                <label for="occupancy" class="block text-sm font-medium text-gray-700">Occupancy Status</label>
                <select id="occupancy" name="occupancy" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    <option value="" disabled selected>Select occupancy status</option>
                    <option value="Own">Own</option>
                    <option value="Rent">Rent</option>
                </select>
            </div>
            
            <fieldset class="border p-4 rounded-lg space-y-4">
                <legend class="text-sm font-semibold text-gray-700 px-2">Homeowner Details (Primary)</legend>

                <div class="space-y-2">
                    <label for="homeowner-name" class="block text-sm font-medium text-gray-700">Homeowner Name</label>
                    <input type="text" id="homeowner-name" name="homeowner-name" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="user-phone" class="block text-sm font-medium text-gray-700">Homeowner Phone Number</label>
                    <input type="tel" id="user-phone" name="homeowner-phone-1" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>

                <div class="space-y-2">
                    <label for="company-email" class="block text-sm font-medium text-gray-700">Homeowner Email</label>
                    <input type="email" id="company-email" name="homeowner-email-1" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>
            </fieldset>

            <div class="flex justify-end pt-2 pb-1">
                <button type="button" id="add-secondary-btn" class="text-sm text-blue-600 hover:text-blue-800 font-medium transition duration-150 ease-in-out focus:outline-none">
                    + Add Secondary Homeowner
                </button>
            </div>

            <fieldset id="secondary-homeowner-fieldset" class="border p-4 rounded-lg space-y-4 hidden">
                <legend class="text-sm font-semibold text-gray-700 px-2">Homeowner Details (Secondary)</legend>

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

            
            <fieldset id="property-address-fieldset" class="border p-4 rounded-lg space-y-4">
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

            <div class="flex items-center space-x-2 pt-2 pb-4">
                <input type="checkbox" id="mailing-same-as-property" checked class="h-4 w-4 text-blue-600 border-gray-300 rounded focus:ring-blue-500">
                <label for="mailing-same-as-property" class="text-sm font-medium text-gray-700">
                    Mailing address is the same as the property address
                </label>
            </div>
            
            <fieldset id="mailing-address-fieldset" class="border p-4 rounded-lg space-y-4 hidden">
                <legend class="text-sm font-semibold text-gray-700 px-2">Mailing Address (Different from Property)</legend>
                
                <div class="space-y-2">
                    <label for="mailing-street-address" class="block text-sm font-medium text-gray-700">Street Address</label>
                    <input type="text" id="mailing-street-address" name="mailing-street-address" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                </div>
                
                <div class="flex space-x-4">
                    <div class="w-1/2 space-y-2">
                        <label for="mailing-state-code" class="block text-sm font-medium text-gray-700">State</label>
                        <select id="mailing-state-code" name="mailing-state-code" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                            </select>
                    </div>
                    <div class="w-1/2 space-y-2">
                        <label for="mailing-zip-code" class="block text-sm font-medium text-gray-700">ZIP Code</label>
                        <input type="text" id="mailing-zip-code" name="mailing-zip-code" pattern="[0-9]{5}" class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
                    </div>
                </div>
            </fieldset>

            
            <div class="space-y-2">
                <label for="individual-name" class="block text-sm font-medium text-gray-700">Individual Submitting Warranty Card</label>
                <input type="text" id="individual-name" name="individual-name" required class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-blue-500 focus:border-blue-500 transition duration-150 ease-in-out">
            </div>
            
            <div class="mt-6">
                <button type="submit" id="submit-btn" class="w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold text-lg transition duration-150 ease-in-out shadow-lg">
                    Create Warranty Card
                </button>
            </div>
        </form>

        <div id="status-message" class="mt-6 p-4 rounded-lg text-center hidden"></div>
    </div>

    <div style="position: absolute; left: -9999px;">
        <table id="warranty-card-template">
            <thead>
                <tr>
                    <td colspan="4" style="text-align: center; font-size: 1.5em; padding: 20px;">
                        Homeowner Information Card
                    </td>
                </tr>
            </thead>
            <tbody>
                <tr class="header-row">
                    <td colspan="4"><span id="template-manufacturer-name" class="manufacturer-name-large"></span></td>
                </tr>
                <tr>
                    <th style="width: 25%;">Sold By (Retailer)</th>
                    <td id="template-retailer-name" class="data-cell" style="width: 75%;" colspan="3"></td>
                </tr>
                <tr>
                    <th>Address</th>
                    <td id="template-retailer-address" class="data-cell" colspan="3">5000 W 95TH ST. STE 250</td>
                </tr>
                <tr>
                    <th>City/State/Zip</th>
                    <td id="template-retailer-zip" class="data-cell" colspan="3">PRAIRIE VILLAGE, KS 66207</td>
                </tr>
                <tr>
                    <th>Date of Sale</th>
                    <td id="template-sale-date" class="data-cell purchaser-name-cell"></td>
                    <td colspan="2" class="data-cell purchaser-phone-cell"></td>
                </tr>
                <tr>
                    <th style="width: 25%;">Purchaser</th>
                    <td id="template-purchaser-1" class="data-cell purchaser-name-cell"></td> 
                    <th class="phone-column">Phone #</th>
                    <td id="template-phone-1" class="data-cell phone-column"></td>
                </tr>
                <tr>
                    <th>Purchaser</th>
                    <td id="template-purchaser-2" class="data-cell purchaser-name-cell"></td>
                    <th>Phone #</th>
                    <td id="template-phone-2" class="data-cell phone-column"></td>
                </tr>
                
                <tr class="header-row">
                    <td colspan="4">SERIAL NUBER: <span id="template-serial-number"></span></td>
                </tr>
                <tr>
                    <th>Mailing address</th>
                    <td id="template-mailing-address" class="data-cell" colspan="3"></td> 
                </tr>
                <tr>
                    <th>City/State/Zip</th>
                    <td id="template-mailing-zip" class="data-cell" colspan="3"></td> 
                </tr>
                <tr>
                    <th>Email</th>
                    <td id="template-email-1" class="data-cell" colspan="3"></td>
                </tr>

                <tr class="header-row">
                    <td colspan="4">Home located at below address</td>
                </tr>
                <tr>
                    <th>Address</th>
                    <td id="template-property-address" class="data-cell" colspan="3"></td>
                </tr>
                <tr>
                    <th>City/State/Zip</th>
                    <td id="template-property-zip" class="data-cell" colspan="3"></td>
                </tr>

                <tr class="header-row">
                    <td colspan="4" class="facility-header">To be filled out by Manufacturing Facility</td>
                </tr>
                <tr>
                    <th colspan="2" style="width: 50%; text-align: center;">Manufactured Date</th> 
                    <th colspan="2" style="width: 50%; text-align: center;">Model</th> 
                </tr>
                <tr>
                    <td colspan="2" style="border-top: none;"></td> 
                    <td colspan="2" style="border-top: none;"></td> 
                </tr>
                <tr>
                    <th class="facility-label">Serial Number</th> 
                    <td colspan="3"></td>
                </tr>
                <tr>
                    <td class="facility-label">Design Wind Zone</td>
                    <td class="facility-label">Design Roof Load</td>
                    <td class="facility-label" colspan="2">Climate Zone</td>
                </tr>
                <tr>
                    <td class="facility-data">Zone I (PSF) ____</td>
                    <td class="facility-data">South (20 PSF) ____</td>
                    <td class="facility-data" colspan="2">Zone 1 ____</td>
                </tr>
                <tr>
                    <td class="facility-data">Zone II (PSF) ____</td>
                    <td class="facility-data">South (30 PSF) ____</td>
                    <td class="facility-data" colspan="2">Zone 2 ____</td>
                </tr>
                <tr>
                    <td class="facility-data">Zone III (PSF) ____</td>
                    <td class="facility-data">South (40 PSF) ____</td>
                    <td class="facility-data" colspan="2">Zone 3 ____</td>
                </tr>
                <tr>
                    <td colspan="2" class="facility-data"></td>
                    <td colspan="2" class="facility-data">Other ________ PSF</td>
                </tr>
                </tbody>
        </table>
    </div>

    <script>
        (function() {
            // US State Codes (50 states)
            const US_STATES = [
                'AL', 'AK', 'AZ', 'AR', 'CA', 'CO', 'CT', 'DE', 'FL', 'GA', 'HI', 'ID', 'IL', 'IN', 'IA', 'KS', 
                'KY', 'LA', 'ME', 'MD', 'MA', 'MI', 'MN', 'MS', 'MO', 'MT', 'NE', 'NV', 'NH', 'NJ', 'NM', 'NY', 
                'NC', 'ND', 'OH', 'OK', 'OR', 'PA', 'RI', 'SC', 'SD', 'TN', 'TX', 'UT', 'VT', 'VA', 'WA', 'WV', 
                'WI', 'WY'
            ];
            
            // Retailer Address for all options
            const RETAILER_ADDRESS = {
                Street: '5000 W 95TH ST. STE 250',
                CityStateZip: 'PRAIRIE VILLAGE, KS 66207'
            };

            // DOM elements
            const form = document.getElementById('parts-form');
            const communitySelect = document.getElementById('community-select');
            const otherCommunityDiv = document.getElementById('other-community-div');
            const otherCommunityInput = document.getElementById('other-community');
            const statusDiv = document.getElementById('status-message');
            const submitBtn = document.getElementById('submit-btn');
            const formMainContent = document.querySelector('form');
            const individualNameInput = document.getElementById('individual-name');
            const homeownerPhone1Input = document.getElementById('user-phone'); 
            const homeownerEmail1Input = document.getElementById('company-email'); 
            const stateCodeSelect = document.getElementById('state-code');
            const secondaryHomeownerFieldset = document.getElementById('secondary-homeowner-fieldset');
            const addSecondaryBtn = document.getElementById('add-secondary-btn');
            const warrantyCardTemplate = document.getElementById('warranty-card-template');
            
            // MAILING ADDRESS DOM REFERENCES
            const mailingSameAsProperty = document.getElementById('mailing-same-as-property'); // CHECKBOX INVERTED
            const mailingAddressFieldset = document.getElementById('mailing-address-fieldset');
            const mailingStreetInput = document.getElementById('mailing-street-address');
            const mailingStateSelect = document.getElementById('mailing-state-code');
            const mailingZipInput = document.getElementById('mailing-zip-code');
            const propertyStreetInput = document.getElementById('street-address');
            const propertyStateSelect = document.getElementById('state-code');
            const propertyZipInput = document.getElementById('zip-code');


            // --- UI TOGGLE LOGIC ---
            
            function toggleMailingAddressFields() {
                const isSame = mailingSameAsProperty.checked;
                
                // Show mailing fields if NOT the same (isSame = false)
                mailingAddressFieldset.classList.toggle('hidden', isSame);
                
                // Set required status based on visibility
                const mailingInputs = mailingAddressFieldset.querySelectorAll('input, select');
                mailingInputs.forEach(input => {
                    input.required = !isSame;
                });

                // If address IS the same, copy Property Address values into Mailing Address fields (for data collection uniformity)
                if (isSame) {
                    mailingStreetInput.value = propertyStreetInput.value;
                    mailingStateSelect.value = propertyStateSelect.value;
                    mailingZipInput.value = propertyZipInput.value;
                } else {
                    // Clear the mailing fields if they are about to be shown (different address)
                    mailingStreetInput.value = '';
                    mailingStateSelect.value = '';
                    mailingZipInput.value = '';
                }
            }

            // Event Listeners for UI interaction
            addSecondaryBtn.addEventListener('click', () => {
                const isHidden = secondaryHomeownerFieldset.classList.toggle('hidden');
                addSecondaryBtn.textContent = isHidden ? '+ Add Secondary Homeowner' : '- Remove Secondary Homeowner';
                
                if (isHidden) {
                    document.getElementById('homeowner-name-2').value = '';
                    document.getElementById('homeowner-phone-2').value = '';
                    document.getElementById('homeowner-email-2').value = '';
                }
            });

            // Initial and ongoing check for address similarity
            mailingSameAsProperty.addEventListener('change', toggleMailingAddressFields);
            propertyStreetInput.addEventListener('input', () => {
                if (mailingSameAsProperty.checked) toggleMailingAddressFields();
            });
            propertyStateSelect.addEventListener('change', () => {
                if (mailingSameAsProperty.checked) toggleMailingAddressFields();
            });
            propertyZipInput.addEventListener('input', () => {
                if (mailingSameAsProperty.checked) toggleMailingAddressFields();
            });
            
            // --- END UI TOGGLE LOGIC ---

            // Function to populate state dropdowns
            function populateStates() {
                let options = '<option value="" disabled selected>Select state</option>';
                US_STATES.forEach(state => {
                    options += `<option value="${state}">${state}</option>`;
                });
                stateCodeSelect.innerHTML = options;
                mailingStateSelect.innerHTML = options; 
            }

            // Function to reset the entire form and show it again
            function resetForm() {
                form.reset();
                statusDiv.classList.add('hidden');
                otherCommunityDiv.classList.add('hidden');
                otherCommunityInput.required = false;
                otherCommunityInput.name = 'unused';
                formMainContent.style.display = 'block';
                secondaryHomeownerFieldset.classList.add('hidden');
                addSecondaryBtn.textContent = '+ Add Secondary Homeowner';
                
                // Reset mailing fields to default checked/hidden state
                mailingSameAsProperty.checked = true;
                mailingAddressFieldset.classList.add('hidden'); 
                mailingAddressFieldset.querySelectorAll('input, select').forEach(input => {
                    input.required = false;
                });
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

            // *** FUNCTION TO FILL TEMPLATE AND EXPORT AS JPEG ***
            document.getElementById('parts-form').addEventListener('submit', function(event) {
                event.preventDefault();

                // Ensure mailing address fields are correctly populated/validated based on checkbox status before final data pull
                toggleMailingAddressFields(); 

                // Final Validation check
                if (!form.checkValidity()) {
                    return; 
                }

                formMainContent.style.display = 'none';
                statusDiv.classList.remove('bg-green-100', 'text-green-800', 'bg-red-100', 'text-red-800');
                statusDiv.classList.add('bg-blue-100', 'text-blue-800');
                statusDiv.innerHTML = 'Creating Warranty Card... Please wait.';
                submitBtn.disabled = true;

                // 1. COLLECT DATA (pulling from Property and Mailing fields)
                const data = {
                    dateSold: form.elements['date-sold'].value,
                    soldBy: form.elements['sold-by'].value,
                    manufacturer: form.elements['home-manufacturer'].value,
                    serial: form.elements['serial-number'].value,
                    community: communitySelect.value === 'Other' ? otherCommunityInput.value : communitySelect.value,
                    lot: form.elements['lot-number'].value,
                    // Property Address
                    pStreet: form.elements['street-address'].value,
                    pState: form.elements['state-code'].value,
                    pZip: form.elements['zip-code'].value,
                    // Mailing Address (Always pulls from mailing fields, which are copied if box is checked)
                    mStreet: form.elements['mailing-street-address'].value,
                    mState: form.elements['mailing-state-code'].value,
                    mZip: form.elements['mailing-zip-code'].value,
                    // Homeowner Info
                    name1: form.elements['homeowner-name'].value,
                    phone1: form.elements['homeowner-phone-1'].value,
                    email1: form.elements['homeowner-email-1'].value,
                    name2: form.elements['homeowner-name-2'].value,
                    phone2: form.elements['homeowner-phone-2'].value,
                    email2: form.elements['homeowner-email-2'].value,
                    submitter: form.elements['individual-name'].value,
                };

                // Prepare date for display (MM/DD/YYYY)
                const formattedDate = new Date(data.dateSold).toLocaleDateString('en-US');
                
                // 2. FILL HIDDEN TEMPLATE
                document.getElementById('template-manufacturer-name').textContent = data.manufacturer;
                document.getElementById('template-retailer-name').textContent = data.soldBy;
                document.getElementById('template-retailer-address').textContent = RETAILER_ADDRESS.Street;
                document.getElementById('template-retailer-zip').textContent = RETAILER_ADDRESS.CityStateZip;
                document.getElementById('template-sale-date').textContent = formattedDate;

                document.getElementById('template-purchaser-1').textContent = data.name1;
                document.getElementById('template-phone-1').textContent = data.phone1;

                document.getElementById('template-purchaser-2').textContent = data.name2 || '';
                document.getElementById('template-phone-2').textContent = data.phone2 || '';
                
                document.getElementById('template-serial-number').textContent = data.serial;
                document.getElementById('template-email-1').textContent = data.email1;

                // Set Mailing Address
                document.getElementById('template-mailing-address').textContent = `${data.mStreet} Lot ${data.lot}`;
                document.getElementById('template-mailing-zip').textContent = `${data.community}, ${data.mState} ${data.mZip}`;
                
                // Set Property Address (Home Located at Below Address)
                document.getElementById('template-property-address').textContent = `${data.pStreet} Lot ${data.lot}`;
                document.getElementById('template-property-zip').textContent = `${data.community}, ${data.pState} ${data.pZip}`;
                
                
                // 3. RENDER HTML TO CANVAS AND DOWNLOAD
                html2canvas(warrantyCardTemplate, {
                    scale: 2, 
                    useCORS: true,
                    allowTaint: true
                }).then(function(canvas) {
                    const image = canvas.toDataURL('image/jpeg', 0.9);

                    const link = document.createElement('a');
                    link.href = image;
                    link.download = `Warranty_Card_${data.lot}_${data.serial}.jpeg`;

                    document.body.appendChild(link);
                    link.click();
                    document.body.removeChild(link);

                    // Show success message
                    statusDiv.classList.remove('bg-blue-100', 'text-blue-800', 'bg-red-100', 'text-red-800');
                    statusDiv.classList.add('bg-green-100', 'text-green-800');
                    statusDiv.innerHTML = '<strong>Success!</strong> Your Warranty Card has been created and downloaded as a JPEG. <br><br> <button id="continue-btn" class="py-2 px-4 bg-blue-600 hover:bg-blue-700 rounded-full text-white font-bold transition duration-150 ease-in-out">Continue</button>';
                    
                    document.getElementById('continue-btn').addEventListener('click', resetForm);
                }).catch(function(error) {
                    console.error('Error creating card image:', error);
                    statusDiv.classList.remove('bg-blue-100', 'text-blue-800', 'bg-green-100', 'text-green-800');
                    statusDiv.classList.add('bg-red-100', 'text-red-800');
                    statusDiv.innerHTML = `<strong>Failed!</strong> There was an error creating the image. Error: ${error.message}`;
                }).finally(() => {
                    submitBtn.disabled = false;
                    formMainContent.style.display = 'block';
                });
            });
        })();
    </script>
</body>
</html>
