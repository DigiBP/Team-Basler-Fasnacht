# Team-Basler-Fasnacht

## Patient Appointment Scheduling Process - Digitalisation of Business Process - FHNW

Our group has decided to model and enhance a Bachelor Thesis of one team member. The thesis focuses on appointment scheduling tools especially in heathcare. At current state, most of hospitals and medical clinics are using phone as a medium to schedule, re-schedule or cancel appointments. This is perceived as an expense that can be eliminated through digitalization.


### <ins>As-Is Process</ins>

The process starts with a phone call from the patient to the secretary of the respective hospital. First, the secretary records all the needed personal data from the patient. After this is done, the secretary checks the availability of the doctors within their calendars and suggest an appointment date. If the first appointment suggestion is fine for the patient the next step will be executed. If not, the appointment finding goes back and forth until both sides are satisfied. The secretary sets the appointment into the calendar of the respective doctor and sends a confirmation per post to the patient. 

![asisprocess](https://user-images.githubusercontent.com/115709891/205094638-ab8e953d-d4c4-4745-8453-fcf302747e28.png)

### <ins>To-Be Process</ins>

To schedule an appointment, the patient have to first enter their basic personal information into the Registration Form (Google Form) such as Name, Email, Mobile, AHV-Number and the reasaon for the appointment. Upon submission of the registration information, the data is processed by services handler, by utilizing a  decision engine which will decide between three options upon which reason was given - remote appointment, physical appointment or the patient will be sent to the emergency.
Within the appointment process, underlying user/business tasks are performed as complimentary part of the process flow. 

<ins>Remote appointment:</ins>

If the reason is "PRE-OP CONSULTATION" a remote appointment is proposed to the patient. A link with further instructions is sent by email upon registration. 

If the selected reason is "SICKNESS" but the PAIN LEVEL is < 5 the DMN is advising a remote appointment.

If selected reason is "Injury" but the PAIN LEVEL is between 1 and 4 and the DAYS DURATION is < 4, the DMN recommends a remote appointment.

<ins>Physical appointment:</ins>

If the reason was "SICKNESS" and the PAIN LEVEL is >= 5 the DMN suggests a physical appointment to the patient. An email with detailed instructions about the appointment is sent to the patient. 

If selected reason is "Injury" but the PAIN LEVEL is between 4 and 6 and the DAYS DURATION is < 4, the DMN recommends a physical appointment.

<ins>Emergency:</ins>

For an emergency advice, the input values for DMN must be "Injury" as reason, >= 7 PAIN LEVEL and >=4 DAYS DURATION.

### <ins>Implementation</ins>

The solution is composed of a combination of a workflow engine solution (Camunda) and connected external services that support different activities within the process and collates the appointment data. 


<ins>Components</ins>
Camunda Workflow: 
The process flow has been created and implemented with Camunda Platform v7.17 using BPMN and DMN. 

MAKE/Integromat Services: 
Sendinblue for Dynamic email notifications
Webhooks (connected to Camunda process instance)
HTTP Requests (connected to Camunda process instance)
Google Forms with Form Validation , for registration data
Calendy Service for Appointment Scheduling


