# business concepts
## what do business care about?
Revenue/'top line'
- money a business generates
- before deductions and costs
profit/'bottom line'
- money a business gets to keep
- after deductions and costs
operations
- things business does that directly aids producing goods/providing services
- ex. manufacturing, distributing
cost centers
- sectors of a business that don't directly add to profit but has a cost to operate
- They do and create something, but the benefit isn't as tangible as a product/service from operations
- *IT department is here*

To increase profit, you have two choices:
1. increase revenue (very hard)
2. reduce costs (relatively easier)
Our job as IT people is to provide systems that are valuable enough so we don't get cut

## Assets and investments
Assets
- Something that is valuable to the company for more than 1 year
  - provides *some* benefit in the future, not just monetary
- not intended for sale
- Type of production cost (cost of running business)
- *people are not assets*, but **information systems are assets**
Investment
- Asset obtained with the intention of generating revenue in the future
- implies risk

## The value of investments and assets
Total cost of ownership (TCO)
- How much something costs to own
- Includes purchase price, operational costs, maintaince costs, and disposal costs
  - operations is usually the biggest (people)
Return on Investment (ROI)
- How much profit comes from an investment
- cost vs profit generated
Cost-benefit analysis
- analysis of the cost of an asset vs it's benfits
- attempts to quantify tangible and non-tangible benefits

When evaluating what projects to move forward with, business consider the ROI and CBA. 
Which ever project has a greater return or benefit compared to it's cost will be higher priority.

# What are information systems?
Interrelated components in an organization that supports the:
- collection
- storage
- processing and organization
of **data** for the purpose of 
- processing the data into information
- spreading the information within the org. to support decision making
  
## Components of Informations Systems
### Hardware
Physical components of systems (computers!)
### Software
Programs that performs tasks on the data.
### Data
Raw facts that become useful in aggregate. **Information** is processed data.
### People
People who work with and help integrate information systems into an organization.
### Processes
Steps that accomplish some task. Information systems are created to improve processes to make the benefit the organization more.

# System Development Life Cycle
>Also known as waterfall methodology or linear methodology
Process that takes problems and turns them into systems that hopefully solve problems. Each step must be complete before moving to the next one.
1. Preliminary analysis
- analyzing the problem to ensure that a system is need
  - are there alternative solutions?
  - is this the correct problem or just a symptom?
  - what is the current solution
- feasbility study is conducted
  - is this project financially, legally, and econoimcally viable?
2. System analysis
- determining **requirements**
  -  what the system needs to do to solve the problem 
3. system design
- determining *how* requirements should be accomplished
  - designing how the technology should work 
4. programming
- making the damn thing
5. testing
- Unit testing
  - making sure individual parts work as intended
- system testing
  - making sure different elements of the system and work together properly
- user acceptance testing
  - does the system meet the standards and needs of the users?
6. implemenation
- putting the system into **production**
  - system in a stable state that is available to org for day to day use
7. maintenance
- bug fixes, upkeep, responding to feed back

## Problems
- Every step is reliant on the completion of the previous step
- Leads to inability to adapt to feed back with going back to the start
  


# Requirements
What a system 'oughta do to solve a problem. (Very important)
## Functional vs. Non-Functional
|Functional| Features of a system|
|Non-functional|How the system has to operate|

Functional requirements focus on what functions a system needs to perform for a business to meet their needs. This manifests as features and capabilities of a system.

Non-functional requirements are how the system operates. How much downtime, how fast it has to respond, the design, etc. This are generally characteristics of the system, not what it's capable of.

## FURPS
|FURPS category| Description|
|Functionality| What the system can do|
|usability|User-friendly-ness of the system|
|Reliability| Uptime, recovery from failure, backups|
|Performance| response time and speed|
|Supportability| How easy is it to maintain this system|

FURPS further divides the requirments into different attributes of the system. 80% of these are non-functional.

# Implementation stratagies
>Once you make something, how do you release it into production?
Each method of implemenation caries cost and a level of risk for the organization and its stakeholders
## Direct cutover
Just take down the old one and put up the new one
- Low cost, high risk
- Good for limited resources
- Causes downtime while legacy (old) system is taken down
- Does not allow for testing
- No rolling back to previous system
## Parallel Operations
Run both systems at the same time
- Highest cost, low risk
- Cost may literally be double from having to maintain the two systems
- zero down time
- If something goes wrong in the new system, legacy system is still present
- easy to rollback system
- slow to transition
- can confuse users
## Pilot operations
Test the system with a sample group before pushing to production
- mid cost mid risk
- You get feedback and testing before production
- Depending on how you select your group, your feedback may be flawed
- Creating this test session sets expectation that thing will change
## Phased operation
features introduced into production one by one in phases
- higher costs, low/middling risk
- Users can give feedback on individual changes
- can be very very long
- introducing too many changes can cause change fatigue

# Managing Projects
Projects have:
- discrete beginning and end
- Produce a unique product
  - unique to the organization that creates it

**The critical path** is the sequecne of steps that when done complete a project in the shortest amount of time. In other words, *the SDLC.*

**Project scope** is what is and isn't required of the project:
- requirements
- schedule/timeline
- deliverables
- personnel
- things that are not being done
  - as a safeguard agains what client might assume we'll provide

**Scope creep** is the uncontrolled growth of project scope.  
Caused by improper docmenation and controlling of the scope, it will cause delays and is 100% guaranteed to happen in every project.

**The iron triangle** is a concept the shows the relationship between 3 aspects of a project:
- cost of making the project
- scheduled completion time
- project scope
Modifying one aspect will affect the others. 