# issue-broker
Close github issues with bounty payments to freelancers.


Scenario
========

#### Login
- Project owner and Freelancer can login to issue broker with github accounts

#### 1. Stage issue
Project owner (PO):
- on github: links github repo to issue brocker with webhook
- on issue broker: sets max hourly rate (eg USD10/h)
- on github: writes a new issue with special text in title or body ```[ib: 1h]```

Issue brocker (IB): 
- reads information about repo issue via webhook
- saves issue information in own database
- lists open issue title and bounty amount at landing page

#### 2. Negotiation

- freelancer (F) applies to open issue   
- project owner selects freelancer

#### 3. Completion

- freelancer makes commits
- project owner closes issue
- issue broker makes payments from project owner to freelancer
