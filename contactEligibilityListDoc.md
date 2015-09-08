# backendWebRTCdocs/contactEligibilityListDoc.md

contactEligibilityList is a new API for Share App Server
It is intended to support the identification of Comcast subscribers eligible to use the Xfinity Share and Xfinity Connect apps running on Android, iOS and X1 clients.

It will allow clients to request user eligibility status for a list of contacts – based on “targets” within each contact, e.g. TNs or email addresses 

- ContactListEligibility API will perform the same validation as is currently performed by RTCGUser GET Entitlement data.
- Responses will contain the same level of eligibility detail as the current Get Entitlement data (for reference see:  Backend WebRTC_RTCGUser_DDD_Baselined_v3.1.2.pdf ) This includes subscribed services (answers the question, is the contact eligible for Share/Stream Live – and, if an X1 sub – Sharecast.)
- Data will be cached; 
- iOS and Android clients will use the data returned to create the contact lists containing eligible subs for each share service type e.g. Sharecast will contain a list of contacts that includes only X1 subscribers.
- Clients will NOT make an additional call to the existing GetEntitlement data when the intended share contact is selected - It is understood that some low incidence of stale cached data might occur, and it is agreed that this is acceptable

Strategies for refreshing and updating the contact list are still under discussion. Agreed so far is that 24 hour cache refresh may be excessive and would provide undue load on the system. 
We are requesting data on average sizes of contact lists to help with API design decisions around processing the contact list and the targets within each list.

 

