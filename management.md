CLARK'S MISCELLANY: MANAGEMENT EDITION
======================================

READING LIST
------------
- Slack (DeMarco)
- Mythical Man Month (Brooks)
- Exponential Organisations (Ismail, Malone, van Geest)
- How to win friends and influence people (Carnegie)
- The Toyota Way (Liker)
- Our Iceberg is Melting (Kotter, Rathgeber)
- Peopleware (DeMarco, Lister)
- The Phoenix Project (Kim)

UPTIME  
------
```
          Day     Month   Year
90      - 2h 24m   3d 1h    36d 12h
95      - 1h 12m   1d 13h   18d 6h
99      - 14m 24s  7h 18m   3d 16h
99.5    - 7m 12s   3h 36m   1d 20h
99.9    - 1m 26s   43m 50s  8h 46m  (three nines)
99.95   - 43s      21m 55s  4h 23m  (three and a half nines)
99.99   - 8.6s     4m 23s   52m 36s (four nines)
99.999  - 0.9s     26s      5m 16s  (five nines)
99.9999 - 0.1s     2.6s     32s     (six nines)
```

DIKM
----
### Data
Metrics - 10 req/sec

### Information
What? - 10 req/sec for system x

### Knowledge
How? - 10 req/sec for system x is good

### Wisdom
Clarity through experience, understanding of consequences - 10 req/sec for system x is good because

FALLACIES OF DISTRIBUTED COMPUTING
----------------------------------
- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology doesn't change
- There is one administrator
- Transport cost is zero
- The network is homogeneous

LAWS, PRINCIPLES AND PHENOMENA
------------------------------
### Baader Meinhoff
Experiencing something shortly after learning it

### Benford's Law
http://www.rexswain.com/benford.html

### Brooks' Law
Adding manpower to a late project makes it later

### Dunning-Kruger
Dumb people think they're smart, smart people think they're dumb.

### Pareto Principle
80/20 - 80% of effects from 20% of causes

### Parkinson's Law
People are promoted to the level of their incompetence

### Postel's law
Be conservative in what you send, liberal in what you receive

### Waterbed theory
Eliminating something (e.g complexity) in one place requires it to be added somewhere else

### Hawthorne/observer effect
Individuals modify/improve performance in response to being observed.

### Chesterton's fence
Don’t ever take a fence down until you know the reason why it was put up

PROGRAMMER'S VIRTUES
--------------------
### Laziness
The quality that makes you go to great effort to reduce overall energy
expenditure. It makes you write labor-saving programs that other people will
find useful, and document what you wrote so you don't have to answer so many
questions about it. Hence, the first great virtue of a programmer. 

### Impatience
The anger you feel when the computer is being lazy. This makes you write
programs that don't just react to your needs, but actually anticipate them. Or
at least pretend to. Hence, the second great virtue of a programmer. 

### Hubris
Excessive pride, the sort of thing Zeus zaps you for. Also the quality that
makes you write (and maintain) programs that other people won't want to say bad
things about. Hence, the third great virtue of a programmer. 

MY MAXIMS/QUOTES
----------------
- Aggressively reduce variance
- Simple > Complex > Complicated
- Intelligence is the ability to adapt to change
- Care more by caring less
- One plus one is many
- Hire slow, fire fast
- A "maybe" is a "no" when hiring
- Don't try and build good systems. Build good teams and you get good systems as an emergent property
- Doing the wrong better doesn't make it right
- One-size-fits-all fits nobody well
- The only thing harder than naming things is renaming them
- Debate, don't dictate
- Throw them in at the deep end with armbands and a lifeguard
- Hire "smart" and "kind"

OTHER MAXIMS/QUOTES
-------------------
- Done is better than perfect
- Now is better than never
- The difficulty lies, not in the new ideas, but in escaping from the old ones, which ramify, for those brought up as most of us have been, into every corner of our minds.
- Perfection is not when there's nothing more to add, but when there's nothing left to remove
- When planning scalability, think x100, design x10, deploy x2 of current traffic
- It is difficult to get a man to understand something when his salary depends on his not understanding it.
- If I had asked people what they wanted, they would have said faster horses -- Henry Ford
- Hanlon's razor: Never attribute to malice that which is adequately explained by stupidity
- Occam's razor: Other factors being equal, simpler explanations are generally better than more complex ones
- Price is what you pay, value is what you get
- If you want to go fast, go alone. If you want to go far, go together.
- You can't fix what you don't measure
- If you plan you can have evolution, if not you need revolution
- What we hope ever to do with ease, we must first learn to do with diligence. -- Samuel Johnson
- Treat servers like cattle, not pets
- It's a fallacy to assume someone who writes incomprehensible code can write a comprehensible comment
- The manager's function is not to make people work, but to make it possible for people to work
- Integrity is when your beliefs, your words, and your actions are all in alignment
- As large as necessary, as small as possible
- Let chaos reign, then rein in chaos
- What you've said hasn't been understood until proven otherwise
- Criticise in private, praise in public

BIG O NOTATION
--------------
```
O(1)       - Constant
O(log n)   - Logarithmic
O(n)       - Linear
o(n log n) - Linearithmic / loglinear
O(n^2)     - Quadratic
O(n^3)     - Cubic
O(n!)      - Factorial
O(n^n)     - Exponential
```

ORDERS OF MAGNITUDE
-------------------
```
10^-24 yocto (y)
10^-21 zepto (z)
10^-18 atto  (a)
10^-15 femto (f)
10^-12 pico  (p)
10^-9  nano  (n)
10^-6  micro (u)
10^-3  milli (m)
10^3   kilo  (k)
10^6   mega  (M)
10^9   giga  (G)
10^12  tera  (T)
10^15  peta  (P)
10^18  exa   (E)
10^21  zetta (Z)
10^24  yotta (Y)
```

DATACENTRE TIERS
----------------
### Tier 1
Single non-redundant distribution path serving the IT equipment
Non-redundant capacity components
Basic site infrastructure guaranteeing 99.671% availability

### Tier 2
Meets or exceeds all Tier 1 requirements
Redundant site infrastructure capacity components guaranteeing 99.741% availability

### Tier 3    
Meets or exceeds all Tier 1 and Tier 2 requirements
Multiple independent distribution paths serving the IT equipment
All IT equipment must be dual-powered and fully compatible with the topology of a site's architecture
Concurrently maintainable site infrastructure guaranteeing 99.982% availability

### Tier 4     
Meets or exceeds all Tier 1, Tier 2 and Tier 3 requirements
All cooling equipment is independently dual-powered, including chillers and heating, ventilating and air-conditioning (HVAC) systems
Fault-tolerant site infrastructure with electrical power storage and distribution facilities guaranteeing 99.995% availability

AAA
---
- Authentication: Who are you?
- Authorisation: Can you access this?
- Accounting: What have you done?

STATISTICS
-----------
- Poisson mean
- Holt-Winters
- Pearson product-moment correlation coefficient
- 3-sigma
- Markov-Chain Montecarlo

LEADERSHIP (POWELL)
-------------------
1. Being responsible sometimes means pissing people off
2. The day your staff stop bringing you their problems is the day you have stopped leading them. They have either lost confidence that you can help them or concluded that you do not care. Either case is a failure of leadership.
3. Don't be buffaloed by experts and elites. Experts often posses more data than judgement. Elites can become so inbred that they produce haemophiliacs who bleed to death as soon as they are nicked by the real world.
4. Don't be afraid to challenge the pros, even in their own backyard
5. Never neglect details. When everyone's mind is dulled or distracted the leader must be doubly vigilant
6. You don't know what you can get away with until you try
7. Keep looking below surface appearances. Don't shrink from doing so just because you might not like what you find
8. Organisation doesn't really accomplish anything. Plans don't accomplish anything, either. Theories of management don't much matter. Endeavors succeed or fail because of the people involved. Only by attracting the best people will you accomplish great deeds
9. Organisation charts and fancy titles count for next to nothing
10. Never let your ego get so close to your position that when your position goes, your ego goes with it
11. Fit no sterotypes. Don't chase the latest management fads. The situation dicates which approach best accomplishes the team's mission
12. Perpetual optimism is a force multiplier
13. Look for intelligence and judgment, and most critically a capacity to anticipate, to see around corners. Also look for loyalty, integrity, a high energy drive, a balanced ego, and the drive to get things done
14. Great leads are almost always great simplifiers, who can cut through argument, debate and doubt, to offer a solution that everybody can understand
15. 40-70 rule: I: Use the formula P=40-70, in which P is probability of success and the numbers indicate the percentage of information required. II: Once the information is in the 40-70 range, go with your gut
16. The command in the field is always right and the rear echelon is wrong, unless proved otherwise
17. Have fun in your command. Don't always run at breakneck pace. Take leave when you've earned it. Spend time with your family. Corollary: surround yourself with people who take their work seriously, but not themselves. Those who work hard and play hard
18. Command is lonely
19. Leadership is the art of accomplishing more than the science of management says is possible.

SDI COLOURS / MOTIVATIONAL VALUE SYSTEM
---------------------------------------
### Altruistic–Nurturing (Blue)
Concern for the protection, growth, and welfare of others

### Assertive–Directing (Red)
Concern for task accomplishment and concern for organization of people, time, money and any other resources to achieve desired results

### Analytic–Autonomizing (Green)
Concern for assurance that things have been properly thought out  and concern for meaningful order being established and maintained

### Flexible–Cohering (Hub)
Concern for flexibility… concern for the welfare of the group… concern for the members of the group and for belonging in the group

### Assertive–Nurturing (Red-Blue Blend)
Concern for the protection, growth, and welfare of others through task accomplishment and leadership

### Judicious–Competing (Red-Green Blend)
Concern for intelligent assertiveness, justice, leadership, order, and fairness in competition

### Cautious–Supporting (Blue-Green Blend)
Concern for affirming and developing self-sufficiency in self and others… concern for thoughtful helpfulness with regard for justice

EIGHT STEPS OF CHANGE (KOTTER)
------------------------------
1. Create a sense of urgency
2. Build a guiding coalition
3. Form strategic vision & initiatives
4. Enlist volunteer army
5. Empower employees & enable action by removing barriers
6. Generate short term wins
7. Consolidate gains & produce more change
8. Anchor new approaches in culture

FOUR STAGES OF COMPETENCE (BURCH)
---------------------------------
1. Unconscious incompetence
2. Conscious incompetence
3. Conscious competence
4. Unconscious competence

14 POINTS ON TOTAL QUALITY MANAGEMENT (DEMING)
----------------------------------------------
1.  Create constancy of purpose for improving products and services.
2.  Adopt the new philosophy.
3.  Cease dependence on inspection to achieve quality.
4.  End the practice of awarding business on price alone; instead, minimize total cost by working with a single supplier.
5.  Improve constantly and forever every process for planning, production and service.
6.  Institute training on the job.
7.  Adopt and institute leadership.
8.  Drive out fear.
9.  Break down barriers between staff areas.
10. Eliminate slogans, exhortations and targets for the workforce.
11. Eliminate numerical quotas for the workforce and numerical goals for management.
12. Remove barriers that rob people of pride of workmanship, and eliminate the annual rating or merit system.
13. Institute a vigorous program of education and self-improvement for everyone.
14. Put everybody in the company to work accomplishing the transformation.

PROJECTS (RACI)
---------------
- Responsible
- Accountable
- Consulted
- Informed

PROJECTS (RAID)
---------------
- Risks
- Assumptions
- Issues
- Dependencies

MOSCOW
------
- Mo: Must Have 
- So: Should Have
- Co: Could Have
- W: Won't happen

OODA (BOYD)
-----------
- Observe 
- Orient
- Decide
- Act

PICK
----
- Possible
- Implement
- Challenge
- Kill

SWOT
----
- Strengths
- Weaknesses
- Opportunities
- Threats

PERSONAL DEVELOPMENT
--------------------
- Belive
- Behave
- Become

PROJECT MANAGEMENT TRIANGLE
---------------------------
- Scope
- Resource
- Schedule

ESTIMATION
----------
```
Time = ( P + 4R + O ) / 6

P = Pessimistic
R = Realistic
O = Optimistic
```

APDEX (performance metric)
--------------------------
```
M = Maximum response time users will tolerate
S(atisfied)  = T < M
T(olerating) = T > M && T < (4M)
F(rustrated) = T > 4M

Apdex = ( Ns + ( Nt / 2 ) ) / N = 0.xx
* 100 for %age satisfaction

0.94 - 1.00 = Excellent
0.85 - 0.94 = Good
0.70 - 0.85 = Fair
0.50 - 0.70 = Poor
0.00 - 0.50 = Unacceptable
```

RESPONSIVENESS
--------------
### 0.1
Response feels instantaneous - 'direct manipulation'

### 1.0
Limit of focus - 'aware that the computer is involved'

### 10
Limit of concentration - likely to context switch

USABILITY GOALS
---------------
- Learnability
- Efficiency
- Memorability
- Errors

REQUIREMENTS
------------
### Functional
* What a system should do: "The system must do x" - "Product" input
- Business rules
- Requirements
- Functions
- Interfaces
- Reporting

### Non-functional
- How a system should do it. "The system shall be x" - "Operations" input
- Qualities
- Constraints
- -ilities
- Performance, capacity, reliability, availability, security, extensibility, etc

CLARK'S...
----------
### Variable
C - Equal to whatever value is required to make the answer correct

### Maxim
"Simple" is to protocols what "Democratic" is to countries

### Razor
Other factors being equal, it's probably the developers

### Number
18446744073709551615

PREFERRED NUMBERS
-----------------
1 2 5 10 20 50 etc

ITSM Journey
------------
- Chaos
- Technology (Infrastrucutre & applications managed as separate domains // separate technology silos)
- Service (Integration and delivery of end-to-end IT services (business solutions) // - Applications vs Infrastructure)
- Customer (IT has mature processes and a single strategy and is focused on the customer // Management of IT supply chain)
- Business (IT is perceived as an internal business partner // IT supports business goals)
- Value (IT customers are the customer of the organization / IT is the business)

FCAPS
-----
- Fault
- Configuration
- Accounting/Administration
- Performance
- Security

TEPES
-----
- Talent
- Education
- Professionalism
- Experience
- Skills

HIRING
------
### Smart
The ability to adapt to change. The technology we use today won't be the technology we use tomorrow

### Kind
The ability to fit in to the team. Don't be a douche.

ITIL Components
---------------
- Incident
- Problem
- Change
- Configuration
- Release
- Service Request

COMMANDER'S INTENT
------------------
- Here's what I think we face.
- Here's what I think we should do.
- Here's why.
- Here's what we should keep our eye on.
- Now, talk to me.

HARDWARE (PICK TWO)
-------------------
- Fast
- Big
- Cheap

HYPE CYCLE
----------
### Technology trigger
A potential technology breakthrough kicks things off. Early proof-of-concept
stories and media interest trigger significant publicity. Often no usable
products exist and commercial viability is unproven.

### Peak of inflated expectations
Early publicity produces a number of success stories—often accompanied by
scores of failures. Some companies take action; many do not.

### Trough of disillusionment
Interest wanes as experiments and implementations fail to deliver. Producers of
the technology shake out or fail. Investments continue only if the surviving
providers improve their products to the satisfaction of early adopters.

### Slope of enlightenment
More instances of how the technology can benefit the enterprise start to
crystallize and become more widely understood. Second- and third-generation
products appear from technology providers. More enterprises fund pilots;
conservative companies remain cautious.

### Plateau of productivity
Mainstream adoption starts to take off. Criteria for assessing provider
viability are more clearly defined. The technology’s broad market applicability
and relevance are clearly paying off.

STAGES OF GROUP DEVELOPMENT (TUCKMAN)
-------------------------------------
### Forming
Team is built. People want to be accepted by others so little controversy or
conflict.  Administrivia of the team is determined: who does what, when to
meet, etc. People are gathering information and impressions on each other and
the task at hand.

### Storming
Trust has developed so members are more willing to express discontent and
challenge others' opinions. A difficult stage for conflict-adverse members.
Emphasise tolerence and understanding of differences. Team must be a "no
judgement" zone with people free to share views and opinions.

### Norming
Team focuses on its goal. Some members may have to compromise their
ideals for the good of the team but all members take responsibility and have
ambition. People may not want to "rock the boat" by sharing controversial
ideas.

### Performing
Team is highly optimised. Job is done smoothly and effectively
without inappropriate conflict and with little need for supervision. Members
are motivated, knowledgeable, competent, autonomous. Dissent is expected and
healthy as part of the improvement cycle.

SITUATIONAL LEADERSHIP THEORY
-----------------------------
## Leadership styles

### S1: Telling
Characterized by one-way communication in which the leader defines the roles of
the individual or group and provides the what, how, why, when and where to do
the task

### S2: Selling
While the leader is still providing the direction, he or she is now using
two-way communication and providing the socio-emotional support that will
allow the individual or group being influenced to buy into the process;

### S3: Participating
This is how shared decision-making about aspects of how the task is
accomplished and the leader is providing less task behaviours while maintaining
high relationship behavior;

### S4: Delegating
The leader is still involved in decisions; however, the process and
responsibility has been passed to the individual or group. The leader stays
involved to monitor progress.

## Maturity levels

### M1: Unable and insecure
They still lack the specific skills required for the job in hand and are unable
and unwilling to do or to take responsibility for this job or task.

### M2: Unable but willing
They are unable to take on responsibility for the task being done; however,
they are willing to work at the task. They are novice but enthusiastic.

### M3: Capable but unwilling
They are experienced and able to do the task but lack the confidence or the
willingness to take on responsibility.

### M4: Capable and confident
They are experienced at the task, and comfortable with their own ability to do
it well. They are able and willing to not only do the task, but to take
responsibility for the task.

## Development levels

### D1: Low competence and high commitment
### D2: Low competence and low commitment
### D3: High competence and low commitment
### D4: High competence and high commitment

TRAITS OF A GOOD LEADER
-----------------------
### Honest
Display sincerity, integrity, and candor in all your actions. Deceptive
behavior will not inspire trust.

### Competent
Base your actions on reason and moral principles. Do not make decisions based
on childlike emotional desires or feelings.

### Forward-looking
Set goals and have a vision of the future. The vision must be owned throughout
the organization. Effective leaders envision what they want and how to get it.
They habitually pick priorities stemming from their basic values.

### Inspiring
Display confidence in all that you do. By showing endurance in mental,
physical, and spiritual stamina, you will inspire others to reach for new
heights. Take charge when necessary.

### Intelligent
Read, study, and seek challenging assignments.

### Fair-minded
Show fair treatment to all people. Prejudice is the enemy of justice. Display
empathy by being sensitive to the feelings, values, interests, and well-being
of others.

### Broad-minded
Seek out diversity.

### Courageous
Have the perseverance to accomplish a goal, regardless of the seemingly
insurmountable obstacles. Display a confident calmness when under stress.

### Straightforward
Use sound judgment to make a good decisions at the right time.

### Imaginative
Make timely and appropriate changes in your thinking, plans, and methods. Show
creativity by thinking of new and better goals, ideas, and solutions to
problems. Be innovative!

3 STAGES OF ORGANIZATIONAL DEVELOPMENT
--------------------------------------
### Stage I: Chaos (fire-fighting mentality)
- Crisis/short-term focus
- Lack of clear direction and goals
- Shifting priorities
- Unclear policies and procedures
- “Us” vs. “them” attitude
- Blame and lack of ownership
- Alienated work force

### Stage II: Stability (back to the basics)
- Clarity of goals and direction
- Consistency in priorities
- Well-defined policies and procedures (technical and personnel)
- Agreement on roles and responsibilities
- Basic management processes rewarded and practiced (goal-setting, performance reviews, etc.)

### Stage III: High performance (outstanding, sustainable results)
* Clear statement of mission that creates sense of esprit de corp.
* Well defined values which result in distinctive culture
* Respect for people that is a deeply ingrained part of culture
* Good communication and information sharing systems
* High involvement and empowerment of people
* Design (work flow, structure, systems) that supports mission and values

THEORY OF ORGANISATIONAL SAFETY (WESTRUM)
-----------------------------------------
### Pathological
- Information is hidden
- Messengers are shot
- Responsibilities are shirked
- Bridging is discouraged
- Failure is covered up
- New ideas are actively crushed

### Bureaucractic
- Information may be ignored
- Messengers are tolerated
- Responsibility is compartmentalised
- Bridging is allowed by neglected
- Organisation is just and merciful
- New ideas create problems

### Generative
- Information is actively sought
- Messengers are trained
- Responsibilities are shared
- Bridging is rewarded
- Failure causes inquiry
- New ideas are welcomed

INVEST (User stories)
---------------------
- Independent: The user story should be self-contained, in a way that there is no inherent dependency on another user story.
- Negotiable:  User stories, up until they are part of an iteration, can always be changed and rewritten.
- Valuable:    A user story must deliver value to the end user.
- Estimatable: You must always be able to estimate the size of a user story.
- Scalable:    User stories should not be so big as to become impossible to plan/task/prioritize with a certain level of certainty.
- Testable:    The user story or its related description must provide the necessary information to make test development possible.

INTRINSIC MOTIVATION (PINK)
---------------------------
### Autonomy
The urge to direct our own lives

### Mastery
The desire to get better and better at something that matters

### Purpose
The yearning to do what we do in service of something larger than ourselves

TWO-FACTOR THEORY (HERZBERG)
----------------------------
### Motivators (satisfaction)
Challenging work, recognition, responsibility

### Hygiene factors (dissatisfaction)
Status, job security, salary, benefits, work conditions

- High motivation + high hygiene: The ideal. Employees motivated with few complaints
- High motivation + low hygiene: Employees motivated but have many complaints. Work is exciting and challenging but salaries and conditions are poor
- Low motivation + high hygiene: Employees have few complaints but work isn't exciting. Job seen as a paycheck.
Low motivation + low hygiene: The worst. Employees not motivated and have many complaints.

LAW OF DEMENTER
---------------
- Each unit should have only limited knowledge about other units: only units "closely" related to the current unit.
- Each unit should only talk to its friends; don't talk to strangers.
- Only talk to your immediate friends.

THE FIVE DYSFUNCTIONS OF A TEAM
-------------------------------
### Dysfunction #1: Absence of Trust
The fear of being vulnerable with team members prevents the building of trust within the team.

### Dysfunction #2: Fear of Conflict
The desire to preserve artificial harmony stifles the occurrence of productive ideological conflict.

### Dysfunction #3: Lack of Commitment
The lack of clarity or buy-in prevents team members from making decisions they will stick to.

### Dysfunction #4: Avoidance of Accountability
The need to avoid interpersonal discomfort prevents team members from holding one another accountable.

### Dysfunction #5: Inattention to Results
The pursuit of individual goals and personal status erodes the focus on collective success.

CHARACTERISTICS OF HIGH PERFORMING TEAMS
----------------------------------------
- Are comfortable asking for help, admitting mistakes and limitations and take risks offering feedback
- Tap into one another's skills and experiences
- Avoid wasting time talking about the wrong issues and revisiting the same topics over and over again because of lack of buy-in
- Make higher quality decisions and accomplish more in less time and fewer resources
- Put critical topics on the table and have lively meetings
- Align the team around common objectives
- Retain star employees

CHANGE MODEL (SATIR)
--------------------
### Late status quo
Things are functioning as normal. Performance is consistent.

### <foreign element>
An event occurs that affects the status quo and requires change.

### Resistance
The requirement for change is resisted. The issue is avoided, ignored or downplayed.

### Chaos
The unknown. Previous assumptions no longer hold true. Relationships change. Performance and quality nosedive. 

### <transforming idea>
A way of adapting to the foreign element is discovered offering a route out of chaos

### Integration
The transforming idea is accepted and integrated in to the system. Performance improves.

### New status quo
The idea is fully integrated and performance has returned to or exceeds the late status quo.

FRAMEWORK FOR THINKING ABOUT SYSTEMS CHANGE (KNOSTER, VILLA, THOUSAND)
----------------------------------------------------------------------
```
V S I R A
  x x x x = Confusion
x   x x x = Anxiety
x x   x x = Resistance
x x x   x = Frustration
x x x x   = False starts
x x x x x = Change
```

- V = Vision
- S = Skills
- I = Incentives
- R = Resources
- A = Action plan

MATURITY
--------
- Adhoc
- Repeatable
- Defined
- Managed
- Optimizing

SMART
-----
- Specific: target a specific area for improvement.
- Measurable: quantify or at least suggest an indicator of progress.
- Achievable: state what results can realistically be achieved, given available resources.
- Responsible: specify who will do it.
- Time-related: specify when the result(s) can be achieved.
