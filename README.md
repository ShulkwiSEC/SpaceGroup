# Paper Working

## Overview

This project is a task management system designed to facilitate interactions between clients and company moderators. The application provides a platform for clients to apply for services and for moderators to manage these requests efficiently.

## Technology Stack

### For Developers:
1. **Templates and Servers:** Flask and Jinja Templates
2. **Database:** SQLite3 (Relational Database)
3. **Static Files:** HTML, JavaScript, CSS

### For Non-Programmers:
The project is divided into two main sections: `Client Stuff` and `Moderators Stuff`.

- **Clients** are users who seek to apply for services provided by the company.
- **Moderators** are company employees such as `Sales Manager`, `Tech Manager`, `Technical Support`, etc.

## Client Section

Features available to clients include:
- **Company Services Gallery**: View the range of services offered.
- **Sign Up**: Create a new account.
- **Login Page**: Access your account.
- **Profile Page**: View and manage your profile.
- **Apply for Services Forms**: Submit requests for services.
- **News and Updates Page**: Stay informed about company updates.
- **Contact and Technical Support Chat**: Communicate with support.
- **Notifications Window**: Receive and view notifications.

## Moderators & System Section

Access Control:
- **Task Manager**: Accessible by all roles (`<999>`).
- **Notebook**: Accessible by all roles (`<999>`).
- **Accounting Page**: Accessible by Manager and Accountant (`<2,1>`).
- **Moderators Management Page**: Accessible by Manager (`<1>`).
- **Technical Support Page**: Accessible by Technical Support and higher (`<3,2,1>`).

### Moderator Roles
Roles are assigned a hierarchical numeric order:
1. **Manager (BOSS)**: Role ID `1`
2. **Accountant**: Role ID `2`
3. **Technical Support**: Role ID `3`
4. **Task Worker**: Role ID `4`
5. **Developer**: Role ID `0`

## Deep Dive Section

### Chat Application

#### Client Side:
- **Sessions & Tickets Manager Bot**: Manage and track support tickets.
- **AI for Auto Answer Bot**: Provide default responses to common questions.

#### Moderators Side:
- **Ticket Management**: Status options include `INTERACT`, `DELETE`, `UPDATE`, `LATE`.
- **Sessions Management**: Status options include `Open`, `Close`, `Not Complete`.
- **Sessions History**: Read-only access to past sessions.

## Workflow

### Example Variables:
```python
c = Client('AHMED OSMAN')
m_Amged = Moderator(name='Amged', role='Manager', role_id=1)
m_Momen = Moderator(name='Momen', role='Accountant', role_id=2)
m_Muona = Moderator(name='Muona Abdulallh', role='Technical Support', role_id=3)
m_Osman = Moderator(name='Osman', role='Task Worker', role_id=4)
```

## Story</br>

m_Amged deploy the webapp and he add some moderators with there role from Add Moderators page,
c will open the website he can browse company service he liked the Some services and he want to applay for it c will go to <singup.html:file> page and create new account then he will be redircet auto to <singin/login.html:file> after he login he will land on <USER.html:file> Main page whice will include some Applaying For Services Forms `From Client we call it Perspective , From Moderators Perspective we call it Task cuz it Some Thing Need to Be Done` After He Applaying For Service A Profile Page has showedup for him telling him ` We Recive Your Apply For Our Service We Work on it  IF you want to see updates click here <Updates:btn> you can browse our gallary While we cooking your order if you want to contact us click <chatapp:btn> to see our Notifications pls click <Notifications:btn> To Drop Down Notifications Window` okay now the client exit he didnt want any thing for now , lets move into Moderators Perspective m_Osman see a applying for service from Tasks Mange Page He See task need to be done for okay he open the task by clicking <openThisTask:btn> `Note Once m_Osman open the task will auto send Notification to the client <Your Service Neer To Complate>` after he click the btn m_Osman get ridrict to another page he see all detaials of the task and the client detaials like: ` ['c Full Name','All Nessary Images','Number Of Pepole c Want to applay for' ...etc]` whice we make him applay for it using a `Servies Forms` now m_Osman Work on the task he can chose want to share the task work with other Task Workers `role: 4` or he can complate it alone , okay now m_Osman Done Task he will click on <dONE:btn> whice will `Send Notification to the client <Your Service Complate>` okay but before he click on <dONE:btn> lets move into m_Muona Perspective
m_Muona open the system app and she see Notification from c he open chat app session m_Muona click <INTERACT:btn> to Iteract with c
c ask some defulte q he get defulte answsers then we want someone to talk while c was opening the chat app window waiting from some one to applay his session to talk with him a Msg arrived says `Hi Your Session Has Been Accpted Now You Can talk` whice happen as refltect from m_Muona click they talk to eche other and they done talk m_Muona click <SessionDone:btn> to close the session, session closed lets back to m_Osman Perspective last we sayed he done from the task and he closed it as (Done) lets move into m_Momen Perspective Once
m_Osman Close the task a new Dues mony process will loged in his logs database <logs.db:file> as task for m_Momen now m_Momen need to complate the service and work with c on the mony and payment stuff once he will click on the not pay loged of c he will redirced to page to contact with c to complate the pay stuff once they compalte and c pay for the service m_Momen click on <PayDone:btn> this will force m_Momen to redirced to a page have a form to log the payment and the mony amount and the clinent name and how much the client pay and all the mony stuff `[pls rember to ask about the payment/mony stuff]`, once m_Momen Clicked on <Save:btn> All the info will be saved into the db <monay.db:file>  Okay  m_Momen Done his work and he Land Again to his profile he see Notifications from m_Amged asking  to get a statistics from the mony process logs database m_Momen open his page <accounter.html> he can see the logs but he wantto export it as pdf,xml,json,word,xlsx file so he can send it to m_Amged He click on <ExportAS:btn> he can see the options he have to export the logs as it he click on pdf where to download window popup and he download it `pls note ask amged to know about the paymentprocess !! for automation`
then he can send it to m_Amged .</br>

### @Story Summary :
1. **Deployment and Setup**: `m_Amged` deploys the web application and adds moderators.
2. **Client Interaction**: `c` browses services, signs up, logs in, and applies for a service. Notifications and updates are handled through the profile page.
3. **Task Management**: `m_Osman` views and manages tasks, interacts with clients, and updates task statuses.
4. **Technical Support**: `m_Muona` handles client support through the chat application.
5. **Accounting**: `m_Momen` processes payments, updates logs, and generates reports.


# Future Enhancements :</br>
- **VIP vs Normal Accounts**: Different tiers for clients.
- **Moderator Chat Application**: Enable chat between moderators.
- **Customer Service Rating**: Allow clients to rate services, with oversight and statistics for managers.