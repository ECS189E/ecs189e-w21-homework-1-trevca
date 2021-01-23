# Homework 1
Trevor Carpenter
SID: *********

## Fields

### textField
A PhoneNumberTextField pointer to access the UI field on the storyboard. Auto formats phone number while user types

### nextButton
A UIButton pointer used primarily to edit the color of the nextButton when a valid phone number is inputted in textField

### errorLabel
A UILable pointer next to the nextButton. While it usually has an empty label field, it will either display errors in red or the successfully entered phone number in black.

### isValidNumber
A Boolean variable to keep track of the phone number validity while the user types so that it doesn't need to be rechecked when the next button is clicked

### isForeign Number
A Boolean variable to keep track of the phone number region code (and if it is not the US) while the user types so that it doesn't need to be rechecked when the next button is clicked

### phoneNumber_e164
The e164 format of the textField's phone number field


## Methods

### nextButtonClick
This function checks for possible errors based on the variables isValidNumber, isForeignNumber, and phoneNumber_e164. See the "Errors" section of this doc for examples. It then sets errorLabel to the corresponding error message. If there are no errors, it sets errorLabel to the entered phoneNumber in e164 format. It also deactivates the keyboard.

### textChange
This function unwraps the textField's text with a guard statement and checks the validity of the number through a try catch block. Based on its region or validity, it may set the isValidNumber or isForeignNumber fields accordingly. If the entered number is valid and ready for the next screen, this function also will set the nextButton color to green, otherwise it will remain gray.

### tap
A function called when the user touches the screen outside the keyboard when typing, disabling the keyboard. Uses the tap gesture recognizer.


## Errors

### No entry error
Displays the message "Click the textbox to enter a number". Triggered by the user clicking the next button without having entered a number.

### Foreign number error
Displays the message "Pleasee enter a US number". Triggered by the user entering a number that is valid but of a different region than US. Example: 61 2 3661 8300

### Invalid number error
Displays the message "Please enter a valid number". Triggered by the user having entered a number that does not pass PhoneNumberKit's number validation. Example: 408





