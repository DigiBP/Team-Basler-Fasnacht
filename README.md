# Team-Basler-Fasnacht

## Patient Appointment Scheduling Process - Digitalisation of Business Process - FHNW

Our group has decided to model and enhance a Bachelor Thesis of one team member. The thesis focuses on appointment scheduling tools especially in heathcare. At current state, most of hospitals and medical clinics are using phone as a medium to schedule, re-schedule or cancel appointments. This is perceived as an expense that can be eliminated through digitalization.

Our project considers two two scenarios:

- create an appointment
- prepare for the first consultation

According to our researches, in most _____ any statistics about medium? How many over phone? What age group?


### <ins>As-Is Process</ins>

The process starts with a phone call from the patient to the secretary of the respective hospital. First, the secretary records all the needed personal data from the patient. After this is done, the secretary checks the availability of the doctors within their calendars and suggest an appointment date. If the first appointment suggestion is fine for the patient the next step will be executed. If not, the appointment finding goes back and forth until both sides are satisfied. The secretary sets the appointment into the calendar of the respective doctor and sends a confirmation per post to the patient. 

![asisprocess](https://user-images.githubusercontent.com/115709891/205094638-ab8e953d-d4c4-4745-8453-fcf302747e28.png)

### <ins>To-Be Process</ins>

To schedule an appointment, the patient have to first enter their basic personal information into the Registration Form (Google Form) such as Name, Email, Mobile, AHV-Number and the reasaon for the appointment. Upon submission of the registration information, the data is processed by services handler, by utilizing a  decision engine which will decide between three options upon which reason was given - remote appointment, physical appointment or the patient will be sent to the emergency.
Within the appointment process, underlying user/business tasks are performed as complimentary part of the process flow. 

<ins>Remote appointment:</ins>

If the reason was OP discussion a remote appointment is proposed to the patient. A link with further instructions is sent by email upon registration. 

<ins>Physical appointment:</ins>

If the reason was sickness, a physical appointment is proposed to the patient. An email with detailed instructions about the appointment is sent to the patient. 

<ins>Emergency:</ins>

The emergency appointments are the "injury" related ones. When injury is selected as reason, an emergency appointment is proposed and the instructions to seek emergency is sent out to the patient´s email. 


### <ins>Implementation</ins>

The solution is composed of a combination of a workflow engine solution (Camunda) and connected external services that support different activities within the process and collates the appointment data. 



