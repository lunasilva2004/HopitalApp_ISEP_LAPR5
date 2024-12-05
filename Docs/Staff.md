# Staff -README.md

## 1. Associated User Stories

- **5.1.12.** - As an Admin, I want to create a new staff profile, so that I can add them to the
hospital’s roster. **(#12)**

- **5.1.13.** - As an Admin, I want to edit a staff’s profile, so that I can update their information. **(#13)**

- **5.1.14.** -  As an Admin, I want to deactivate a staff profile, so that I can remove them from
the hospital’s active roster without losing their historical data. **(#14)**

- **5.1.15.** - As an Admin, I want to list/search staff profiles, so that I can see the details,
edit, and remove staff profiles. **(#15)**

### 1.1. Customer Specifications and Clarifications

**5.1.12.**

* The functionality for creating staff profiles is essential for ensuring that new healthcare professionals (doctors, nurses, technicians) are properly registered in the system. These profiles are necessary for the correct allocation of resources when planning surgeries. 

* Clarifications provided by the client:

Staff ID vs. License Number: The Staff ID is automatically generated by the system upon profile creation, while the License Number is assigned by external professional organizations (e.g., "Ordem dos Médicos").

Roles and Specializations: Each staff member can have a specific specialization (e.g., orthopedic surgeon, anesthesiologist), and these specializations are crucial for surgery scheduling as different procedures require different healthcare professionals.

Registration Fields: The registration fields include name, license number, specialization, and contact information. The license number is validated to ensure it is unique and correctly assigned by the respective professional guild.

**5.1.13.**

* The functionality to edit staff profiles allows administrators to keep the information of healthcare professionals (doctors, nurses, technicians) up-to-date in the system.

* Clarifications provided by the client:

Editable fields: The Admin can edit the staff member’s name, specialization, email, and phone number. The license number cannot be directly changed by the Admin and is reserved for a specific update process.

Data validation: During the editing process, the system must ensure that the email and phone number are unique to avoid duplication.

Deactivation: Deactivating a staff profile is not part of the editing process and must be handled by a separate function.

**5.1.14.**

* The functionality to deactivate a staff profile allows the administrator to temporarily or permanently suspend a healthcare professional’s access to the system without deleting the profile entirely. This is useful in cases of contract termination or extended absence, ensuring that data is preserved for future reference.

* Clarifications provided by the client:

Deactivation vs. Deletion: Deactivation does not remove the staff profile from the system; it is kept in the database for future reference, but the staff member loses access to system functionalities.

Access and Permissions: Once deactivated, the staff member can no longer perform or access system functions associated with their role, such as requesting or performing surgeries.

Reasons for Deactivation: This process can be used in cases such as temporary leave, the staff member leaving the hospital, or administrative decisions.

**5.1.15.**

* The functionality to list and search staff profiles allows the administrator to view all healthcare professionals registered in the system and search for specific profiles based on criteria like name, license number, or specialization. This is crucial for efficient management of hospital staff and proper resource allocation.

* Clarifications provided by the client:

Search Criteria: Administrators will be able to search staff profiles using various criteria such as name, specialization, or license number.

Applicable Filters: The system should allow administrators to apply filters to refine the results, such as listing only active or inactive staff profiles.

Search Purpose: Searching staff profiles is useful for administrative reviews, checking operational history, and assigning staff for upcoming operations.


## 2. Requirements

## Acceptance Criteria

**5.1.12.**
- Admins can input staff details such as name, license number, specialization, and contact information (email and phone).

- The system generates a unique Staff ID upon profile creation.

- The License Number must be validated to ensure it is unique and legally compliant with the relevant 
professional body.

- The profile is stored securely in the system, and access to it is governed by role-based permissions.

**5.1.13.**
- Admins can search for and select a staff profile to edit.

- Editable fields include contact information, availability slots, and specialization.

- The system logs all profile changes, and any changes to contact information trigger a
confirmation email to the staff member.

- The edited data is updated in real-time across the system.

**5.1.14.**
- Admins can search for and select a staff profile to deactivate.

- Deactivating a staff profile removes them from the active roster, but their historical data (e.g.,
appointments) remains accessible.

- The system confirms deactivation and records the action for audit purposes.

**5.1.15.**

- Admins can search staff profiles by attributes such as name, email, or specialization.

- The system displays search results in a list view with key staff information (name, email,
specialization).

- Admins can select a profile from the list to view, edit, or deactivate.

- The search results are paginated, and filters are available for refining the search results


#### Use Cases:

For this user story, we can define the following use case:

1. Create a new staff profile:

The Admin enters the staff member’s name, license number, specialization, and contact information.
The Admin confirms the data and submits the profile for creation.
The system validates that the license number is unique and legally valid.
The system generates a unique Staff ID for the new profile.
The system displays a success message to the Admin.

2. Edit Staff Profile:

The Admin selects an existing staff profile.
The Admin edits the name, specialization, email, and/or phone number.
The system validates if the email and phone number are unique.
The Admin confirms the changes.
The system saves the changes and displays a success message.

3. Deactivate Staff Profile:

The Admin selects an active staff profile.
The Admin triggers the deactivation action for the profile.
The system deactivates the staff profile, removing their access to system functionalities.
The system displays a confirmation message that the profile has been deactivated.

4. List/Search Staff Profiles:

The Admin requests a list of all staff profiles.
The system displays all staff profiles, showing essential details such as name, specialization, and status (active/inactive).
The Admin enters search criteria like name or specialization.
The system returns staff profiles that match the search criteria.
The Admin can refine the search by applying filters like profile status (active/inactive).


#### Functionality:

**5.1.12.**
The Admin enters information such as the staff member’s name, specialization, license number, and contact information.The system generates a Staff ID for each new entry.Validation ensures that the License Number is unique and correctly assigned by external guilds.

**5.1.13.**
The Admin can update a staff member’s information, such as name, specialization, email, and phone number. The system ensures that this data is unique and complies with business rules.

**5.1.14.**
Deactivating staff profiles blocks their access to the system but keeps the profile and history intact for future reference. The profile is marked as inactive within the system and does not appear in active staff lists but can still be accessed by administrators for data consultation.

**5.1.15.**
The list/search functionality allows the Admin to quickly find the necessary healthcare professionals. Searches can be conducted based on various criteria, such as name or specialization, and filters can be applied to further refine the displayed results.

#### Understanding:

**5.1.12.**
The Staff ID is generated by the system and is unique within the system. The License Number is externally assigned and cannot be generated by the system; it must be entered manually by the Admin.

**5.1.13.**
The license number of a staff member cannot be edited through the profile editing process. The system performs a uniqueness check for email and phone number during the editing process to ensure no duplicates exist.

**5.1.14.**
Deactivating a staff profile removes their access to the system while keeping their data (e.g., personal details, license number, and history) intact. The profile remains in the system for future reference or audits but is marked as inactive, preventing further actions by the staff member.

**5.1.15.**
The system must allow the Admin to view all staff profiles, both active and inactive, and search based on criteria like name, license number, or specialization. Filters can be applied to refine the results, such as showing only active profiles. This ensures efficient access to staff information for administrative and operational needs.

## 4. Input and Output Data

### **_5.1.12_**

* Input Data:
    * First Name 
    * Last Name
    * Role
    * Specialization
    * Email
    * Phone Number
    * Status

* Output data:
    * The staff including License Number generated.
    * (In)Success of the operation.

------------------------------------------------

### **_5.1.13_**

* Input Data:
  * Patient's unique identifier (ID) for search. 
  * Updated patient information, including:
    * First Name 
    * Last Name
    * Role
    * Specialization
    * Email
    * Phone Number
* Output Data:
  * The updated staff including the License Number generated.
  * (In)Success of the operation.

------------------------------------------------

### **_5.1.14_**

* Input Data:
  * Staffs's unique identifier (ID).
* Output data:
  * (In)Success of the operation.

------------------------------------------------

### **_5.1.15_**

* Input Data:
  * Name, email, or specialization
* Output data:
  * (In)Success of the operation.
  * List of Staffs.

------------------------------------------------

## 5. Use Cases

<p align="center">
  <img src="General_Documentation/UseCaseDiagrams/svg/Staff_UseCaseDiagram.svg" alt="Staff Use Case Diagram">
</p>


------------------------------------------------

## 6. General Information

- **_Staff:_** 

- **Attributes:** Represents the profile and key information of a healthcare staff member involved in patient care and operations

  - `ID` - Unique Identifier;
  - `FirstName` - The first name of the staff member.
  - `LastName` - The last name of the staff member.
  - `Name` -  The full name of the staff member, combining FirstName and LastName.
  - `Role` - The professional role of the staff member within the organization (e.g., Nurse, Doctor).
  - `LicenseNumber` -  A unique number assigned to the staff member based on their role and a sequential identifier.
  - `Specialization` - The specific area of expertise of the staff member
  - `Email` - The staff member's primary email contact.
  - `PhoneNumber` - The staff member's primary phone contact.
  - `IsActive` - A boolean flag indicating if the staff member is currently active within the organization.
  - `Slots` - A list representing the availability slots of the staff member for scheduling purposes.

------------------------------------------------