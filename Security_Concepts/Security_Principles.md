CIA Triad

- Confidentiality  
- Integrity  
- Availability

PIM

- Privileged Identity Management  
- Translate a user's role within an organisation into an access role on a system

PAM

- Privileged Access Management  
- Management of the privileges a system's access role has

Security Models

- Bell-La Padula Model  
  - Used to achieve confidentiality. This model has a few assumptions, such as an organisation's hierarchical structure it is used in, where everyone's responsibilities/roles are well-defined  
  - Granting access to pieces of data (objects) on a strictly need to know basis. This model uses the rule "no write down, no read up"  
  - Advantage  
    - Policies in this model can be replicated to real-life organisations hierarchies  
    - Simple to implement and understand  
  - Disadvantage  
    - User may not have access to an object, they will know about its existence  confidentiality issue  
    - Relies on a large amount of trust within the organisation  
- Biba Model  
  - Applies the rule to objects (data) and subjects (users) that can be summarised as "no write up, no read down"  
  - Subjects can create or write content to objects at or below their level but can only read the contents of objects above the subject's level  
  - Advantage  
    - Simple to implement  
    - Resolves the limitations of the Bell-La Padula model, address both confidentiality and data integrity  
  - Disadvantage  
    - Many levels of access and objects  
    - Often results in delays within a business
