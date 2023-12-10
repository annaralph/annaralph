Test Task for Business/System Analyst Position
ABC Bank Solution requirements


Questions and assumptions.

Question
Assumption
Do you use an in-house DWH or on 3rd party side to store customer personal data?
Yes. As credit scoring is supposed to use not only data from external sources (like credit bureaus, mobile, and utility operators, etc) but also customer credit and request history inside the service.
Does the choice of data storage inside /outside the service model influence the speed and efficiency of operations?
Besides the age 18+ required are there any limitations or legal restrictions depending on the customer profile? Is credit available only for citizens of this country? 
Yes. Credit could be available only in certain country. The system checks the customer device location/format of the telephone number.


Do you use Black lists and Fraud lists to prevent undesirable customers from applying? 
Yes. A black list can be formed of persons whose usage of the service was earlier admitted as not appropriate or illegal.


How do you process a customer selfie, which is submitted while onboarding? What service is used to verify that on the selfie and in the international passport is the same person?
Verification is processing via a partner AI service.
Do you store the personal data immediately after it was provided? Or only after verification (for example, after matching an applicant's face with passport data)?


Only when the data is verified to avoid access data storage.

However, this option should be estimated by SMEs to decide whether the value of customer data for a business exceeds the storage expenses.
Do you store selfies too as a customer document?
Yes, but its storage term can differ from other data.

I would assume that this storage is not necessary for future interaction with customers, considering the huge size of this type of document. However, they have to be stored for Credit Control could verify the legitimacy of the loan rejection or approval.

The minimum time of Customer document storage should be defined by the legal department.
After the credit availability is approved does the system give a possibility to order the credit immediately on the app screen? Or only accept a request and then send the results by email?
On the app screen.

Alternative path: Here could be set the time out rule: if a decision is made in X seconds, a credit offer becomes available directly on the app. If the decision requires more time, the Customer sees the message “Your request is submitted. We’ll send you an email with your credit limit”.





2. ABC mobile app new user onboarding process.

2.1. High-level use case diagram





2.2. Process Diagram 



2.2. Process description (highlights to the diagram)

To obtain a loan a new customer selects a sign-up button. Then Customer fills in the email and mobile, the system checks the correctness of the data input. The telephone number should be verified to match the international format and verify the customer’s country by a code and by system location. If the customer's location or phone number does not belong to the country of service, the Customer should see a message, that access is not available.
The amount of sign-up attempts should be limited to prevent fraud. The maximum amount should be established by the Business Owner of the system with the possibility of changing it. Default = 5.
After a successful check of primary contact data, the Customer fills in the data fields, attaches the documents, and gives permission for access to the contact list.
All customer data should be stored in the temporary repository and then checked by back-end systems.
The system checks if such customer data were not used before for another customer ID, stores a scanned copy of the Customer's Passport and selfie for future verification, and with the help of an AI-based model checks if the face on the selfie matches the photo in the international passport. 
The system sends the customer data to the storage.
When the customer data is collected the system processes it with the help of decisioning model/system, applying it to internal and external repositories and sources to estimate customer credit history and solvency.
When the credit score is calculated and the decision is made, the decision result - either negative or positive - should be submitted to the customer profile in the CRM system. Later it should be available for the Credit Control check.
The system establishes the credit limit for a Customer. The process ends. Starts the process of making an order. 

The detail level of a process doesn’t imply all the details and internal processes and model logic. Also, a system no-answer alternative path is not included, as it’s assumed as a default logic for whole the app. 



2.3. Data model



