### Problem Statement
#### Bureau: Building a Real-Time Fraud Detection API to detect and curtail frauds


#### Theme: Develop an API that uses machine learning to analyse payment transactions and identify suspicious activity in real-time.

### Building a Real-Time Fraud Detection API to detect and curtail frauds

<details>
  <summary>Click to show Details</summary>



In the fast-paced realm of digital payments, ensuring the safety and reliability of transactions is of utmost importance. As the Unified Payments Interface (UPI) gains widespread acceptance in India and beyond, an urgent call arises for a robust system capable of promptly identifying and flagging potentially suspicious transactions.

While UPI was originally available in mainly one form factor, cards and other form factors have been added to the same. Fintech innovation leads to fraud innovation as well since access to technology is fairly democratised.

The other trend we’ve been noticing is that Fraud is no longer a single player game - that is to say, one off projects by one fraudster are rare. The industrialisation of fraud via syndicates and fraud rings across India and the world has made it harder to prevent abuse - but our mission at Bureau is to empower fintech and financial sector companies with the tools and know-how in order to make transacting online safer for all customers.

A common way in which customers lose money is via social engineering fraud which can happen when a fraudster calls or contacts a customer and gains their trust by pretending to be a person in a position of power or authority to get them to reveal account information or one time passwords, leading to an account takeover. Typically, when such a fraud occurs - the usage patterns change and our role as an infrastructure company is to be able to detect anomalies that are indicative or risky or fraudulent behaviour.

As part of this hackathon, we want to see if you can get into the minds of fraudsters and think about the different ways in which they would try to take advantage of account information obtained from a user. What would the cat and mouse game of figuring out patterns and anomalies look like when API-fied?

For example, if the victim is someone who never fills fuel but a transaction at a petrol bunk to the tune of 40,000 rupees is seen ( which would indicate filling several trucks worth of Diesel ) - then it is certainly likely that there is some anomalous behaviour underway that needs to be investigated by adding additional and strategic friction before letting the payment go through.

To solve this challenge, develop an API that does real-time monitoring and analyses transactional attributes such as amount, frequency, location, device usage, and transaction timing, as well as user-specific parameters like spending behaviours, transaction history, geographic location, device details, and account activity, by harnessing machine learning algorithms such as i-Forest, ECOD , auto encoders, local outlier factor (LOF), and others.

The solution should be able to flag these scenarios:

If the user tries to make transactions with a total cumulative amount >= to 70% of the card balance and the balance >= Rs 3,00,000 within 12 hours. (RULE-001)
Users transact from more than 5 locations (the minimum difference is 200KM between two locations) and transact with that card for more than 1,00,000 Rs within a 12-hour window. (RULE-002)
If the transactions from a card don’t follow the coherent pattern of the last 12-hour/1-day/7-day window. (RULE-003)
If the transaction doesn’t follow a coherent pattern with the merchant category code of the last 3-day/7-day/30-day for the card (RULE-004)
The input is a json payload containing relevant fields for the above scenarios:

{
"mti": "0100",
"processingCode": "000000",
"transactionAmount": "0000000000.00",
"dateTimeTransaction": "2412192200",
"cardholderBillingConversionRate": "61000000",
"stan": "13244",
"timeLocalTransaction": "192200",
"dateLocalTransaction": "2412",
"expiryDate": "2306",
"conversionDate": "0911",
"merchantCategoryCode": "5969",
"posEntryMode": "810",
"acquiringInstitutionCode": "013992",
"forwardingInstitutionCode": "001695",
"rrn": "1122033441",
"cardAcceptorTerminalId": "8999840",
"cardAcceptorId": "89050840 ",
"cardAcceptorNameLocation": "NETFLIXUS",
"cardBalance": "0000000000.00",
"additionalData48": "T",
"transactionCurrencyCode": "840",
"cardholderBillingCurrencyCode": "840",
"posDataCode": "102510800600084063368",
"originalDataElement": "01001324424121922000000001399200000001695", "channel": "ECOM",
"encryptedPan": "Kg1WR6lwTruEPIDK0GS4w82/wrFeXTU5SjD9TfyUXmc=", "network": "MASTER",
"dcc": false,
"kitNo": "1020001031",
"factorOfAuthorization": 0,
"authenticationScore": 0,
"contactless": false,
"international": true,
"preValidated": false,

"enhancedLimitWhiteListing": false, "transactionOrigin": "ECOM", "transactionType": "ECOM", "isExternalAuth": false, "encryptedHexCardNo":

"2a0d5647a9704ebb843c80cad064b8c3cdbfc2b15e5d35394a30fd4dfc945e67", "isTokenized": false,
"entityId": "EKCZSH8MA5",
"moneySendTxn": false,

"mcRefundTxn": false, "mpqrtxn": false, "authorisationStatus": true, "latitude": "28.644800", "longitude":"77.216721"

}

The output response must be in json and should follow this structure: {

"status": "ALERT/OK",
"ruleViolated": ["RULE-001", "RULE-003"], "timestamp": "unix timestamp in string"

}

Submission Format:

Fully functional API hosted on any freeware server . If required we can provide AWS Infrastructure. API documentation if the specifications are different than above.
Source Code files
Summary of the solution that includes Architecture and Flow Diagram

</details>


Workflow of the project:

  [![Workflow](https://github.com/poorvika7khanna/fraud-detection-backend/blob/main/Workflow_fraud_detection.png)]()


Workflow of the APIs:

  [![Workflow](https://github.com/poorvika7khanna/fraud-detection-backend/blob/main/Workflow_fraud_detection.png)]()


