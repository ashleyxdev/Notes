# Risk Management

## Phases

| Phase                                    |                  Main action | How it reduces uncertainty                       |
| ---------------------------------------- | ---------------------------: | ------------------------------------------------ |
| Identify                                 |          Find possible risks | Turns unknowns into known items                  |
| Communicate                              |             Share & escalate | Ensures aligned decisions and early action       |
| Assess                                   | Analyze probability & impact | Replaces guesswork with estimates                |
| Prioritize                               |                 Score & rank | Focuses effort on biggest uncertainties          |
| Respond (Avoid/Mitigate/Transfer/Accept) |        Decide & plan actions | Lowers likelihood/impact or moves responsibility |
| Preventive tasks                         |           Implement controls | Reduces chance of occurrence                     |
| Contingency planning                     |      Prepare "if-then" plans | Cuts reaction time and confusion if risk happens |
| Register & Track                         |         Document and monitor | Keeps visibility, enables adjustment & learning  |

| **Risk Type**      | **Examples**                        | **How to Mitigate**                            |
| ------------------ | ----------------------------------- | ---------------------------------------------- |
| Schedule           | Late hardware, review delays        | Realistic schedules, buffers, tracking tools   |
| Scope              | Scope creep, unclear requirements   | SRS, sign-off, change control                  |
| Resource           | Staff unavailable, skill gap        | Training, backup staff, proper allocation      |
| Cost               | Cost overruns, Inexperienced PM     | Accurate estimation, contingency budgets       |
| Quality            | Poor deliverables                   | QA plan, reviews, testing                      |
| Technological      | Unproven tech, integration issues   | Feasibility study, prototypes, expert help     |
| Delivery           | Fails performance/functionality     | Load tests, prototypes, requirement validation |
 
# Software Project Management

## Phases

| **Phase**                | **Meaning / Purpose**                                          | **Key Activities**                                                                                                                                                                                                                                                                                                                                                                                                                                           | **Outcome**                                     |
| ------------------------ | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------- |
| **1. Feasibility Study** | Checks if project is worth doing and has a valid business case | - Initial requirements elicitation<br>- Estimate cost, benefits, effort<br>- Technical, financial, operational feasibility                                                                                                                                                                                                                                                                                                                                   | Decision whether to start project               |
| **2. Planning**          | Lays out how the project will be executed                      | - Define scope & objectives<br>- Prepare schedule, resources, budget<br>- Risk management plan<br>- Outline plan for full project, detailed plan for near-term                                                                                                                                                                                                                                                                                               | Approved project plan                           |
| **3. Project Execution** | Actual development and delivery of the system                  | **Requirements Analysis** – detailed user & system requirements<br>**Architecture Design** – system-level design<br>**Detailed Design** – component-level design<br>**Code & Test** – implement and unit test modules<br>**Integration** – combine modules & verify interactions<br>**Qualification Testing** – full system testing<br>**Installation** – deploy into operational environment<br>**Acceptance Support** – fix issues & support stabilization | Fully developed, installed, and accepted system |

## How software project manager chooses suitable methods

| **Selection Factor**                         | **Description**                                                                           | **How It Influences Choice**                                        | **Examples (Agile / DevOps / Waterfall)**                                                                 |
| -------------------------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **1. Nature of Activities**                  | Understanding what tasks need to be performed (testing, design, estimation, coding).      | Determines which specific *methods* are needed for each activity.   | Test case creation → Testing methods; User stories → Agile; Documentation → Waterfall                     |
| **2. Project Characteristics**               | Includes project size, complexity, requirement stability, risk, and customer involvement. | Helps choose a methodology that fits project uncertainty and scale. | Rapidly changing requirements → Agile; High-risk system → Waterfall; Large complex system → Hybrid        |
| **3. Organizational Culture & Constraints**  | Company preferences, standards, maturity, and work culture.                               | Methodology must align with organizational norms.                   | Documentation-heavy culture → Waterfall; Flexible startup culture → Agile; Automation-driven org → DevOps |
| **4. Tools, Resources & Skill Availability** | Availability of tools (CI/CD, backlog tools) and team skills.                             | SPM selects methods the team can realistically execute.             | Skilled in CI/CD → DevOps; Skilled scrum team → Agile; Strong documentation skills → Waterfall            |
| **5. Integration of Multiple Methods**       | Large projects require multiple specialized methods combined under a methodology.         | Ensures all chosen methods are compatible and cohesive.             | Requirements engineering + testing + configuration management → Integrated into Agile/Waterfall           |

| **Methodology** | **When SPM Selects It**                                                                          | **Methods Used Inside It**                                    | **Why It’s Suitable**                                    |
| --------------- | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------- | -------------------------------------------------------- |
| **Agile**       | Requirements change often; customer wants involvement; fast delivery needed; small–medium teams. | User stories, sprints, backlogs, continuous testing.          | Highly adaptable, iterative, reduces uncertainty.        |
| **DevOps**      | Continuous delivery needed; frequent deployments; cloud-based systems; automation needed.        | CI/CD, automated testing, IaC, monitoring.                    | Fast delivery, automation, better Dev–Ops collaboration. |
| **Waterfall**   | Stable requirements; strict documentation; regulated industries.                                 | Requirement specification, design documents, phase sign-offs. | Predictable, structured, documentation-focused.          |

# Business case and Business plan

## elemnts / phases

| **Concept**       | **Meaning**                                                      | **Key Steps**                                                                                                                    |
| ----------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **Business Case** | Justifies why project should be done; compares costs vs benefits | Identify problem → Proposed solution → Cost & benefit estimation → Cost–benefit analysis → Risks → Alternatives → Recommendation |
| **Business Plan** | Describes how project will be executed                           | Objectives → Market analysis → Feasibility → Financial plan → Implementation plan → Risk plan → KPIs → Approval                  |

## difference

| **Basis of Difference**    | **Business Case**                                                                                                            | **Business Plan**                                                                                          |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Purpose**                | Justifies *why* a project should be undertaken (cost–benefit justification).                                                 | Explains *how* the project or initiative will be executed and managed.                                     |
| **Focus**                  | Focuses on **value**, **benefits**, **costs**, and **feasibility**.                                                          | Focuses on **strategy**, **implementation**, **operations**, and **resources**.                            |
| **Timing**                 | Prepared **before** the project starts to decide whether to proceed.                                                         | Prepared **after** approval to guide the execution of the project.                                         |
| **Main Question Answered** | “Is this project worth doing?”                                                                                               | “How will we do this project successfully?”                                                                |
| **Contents**               | Problem identification, proposed solution, cost analysis, benefit analysis, ROI, risks, alternative options, recommendation. | Objectives, scope, schedule, resource plan, budget, market analysis, implementation plan, risk plan, KPIs. |
| **Level of Detail**        | High-level, decision-oriented.                                                                                               | Detailed and operational.                                                                                  |
| **Outcome**                | Go / No-go decision for the project.                                                                                         | Roadmap for executing and managing the project.                                                            |
| **Example**                | A business case explaining why an e-commerce website will increase revenue and is worth building.                            | A business plan describing how the website will be developed, marketed, deployed, and maintained.          |

# 4 P's

| **P**       | **Meaning**                                                                | **Key Activities / Elements**                                                                                         | **If Neglected (Example)**                                                                                                                |
| ----------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **People**  | Most crucial resource; individuals involved in development and management. | Recruitment, training, motivation, communication, team building, conflict management.                                 | Inexperienced developers → poor code quality; team conflicts → delays. **Example:** Banking app crashes due to poorly trained developers. |
| **Product** | Understanding what software must do; defining objectives and scope.        | Requirements definition, problem decomposition, identifying constraints, cost & schedule estimation.                  | Unclear requirements → scope creep. **Example:** Ecommerce site fails to support online payments because requirements were incomplete.    |
| **Process** | Framework/model used to build the software.                                | Selecting and following models like Waterfall, Agile, Spiral, RAD, Prototyping; ensuring proper workflow and reviews. | Wrong process → rework and inefficiency. **Example:** Startup uses Waterfall, causing delays when requirements keep changing.             |
| **Project** | The organized effort to deliver the product within time, cost, and scope.  | Planning, scheduling, monitoring, risk management, quality control, reporting.                                        | Poor planning → missed deadlines; cost overruns. **Example:** Hospital system delayed because no proper scheduling or tracking was done.  |

# Stake-holders

| **Stakeholder Type**                                         | **Meaning**                                                                       | **Examples**                                                                      | **Role / Importance**                                                                                                                                                        |
| ------------------------------------------------------------ | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Internal to the Project Team**                          | Directly part of the core project team; work under project manager’s control.     | Developers, testers, designers, business analysts, team leads                     | Perform daily project tasks (coding, testing, documentation). Directly impact quality and progress. Miscommunication here causes major project delays.                       |
| **2. External to Project Team but Within Same Organization** | Not in the core team but belong to the same company; provide support when needed. | IT support, DBAs, system admins, network team, security auditors, senior managers | Offer specialized services (infrastructure, database, networks). Involvement is negotiated. Delays from them can slow deployment/testing.                                    |
| **3. External to Both Project Team & Organization**          | Stakeholders outside the company who interact via contracts or usage.             | Customers, end-users, vendors, contractors, outsourcing partners                  | Influence requirements, approve deliverables, provide services. Customer satisfaction determines project success. Misunderstanding them leads to building the wrong product. |
