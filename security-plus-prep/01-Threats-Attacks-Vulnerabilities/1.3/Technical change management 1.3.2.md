Execute the plan, put the management process into action. There is no such thing as simple upgrade, can have many moving parts and seperate events may be requiered. ''What'' need to change, and the technical team is the ''how''. 

## Allow or deny list 
Vulnerabilities, trojan horses, malwares, basically any application can be dangerous. Security policy can control app execution. 
- Allow list : nothing runs unless it's approved, very  restrictive 
- Deny list : nothing on the bad list can be executed, anti-virus/anti-malware have it. 
## Restricted activities 
the scope of a change is important. Defines eactly which components are covered, a change approval isn't a permission to make any change ! the change control has to be very specific. The scope may need to be expanded duing change window, it's impossible to prepare for all outcomes. Well documentated change management process determines the next step
##  Downtime
Services will eventually be unavailible, the change process can be disruptive, usually scheduled during non.production hours. If possible avoid it specially for 24h/24h productions, switch to a secondary system in the meantime. Minimize any downtime events, the process should be as automated as possible. Switch back to secondary if issues appear, part of the backout plan. Send emails and calendar updates. 
## Restarts
Reboot OS may be requiered or power down on physically. Can the system recover from a power outage ? 
Services : stop and restart the service or daemon (linux). Applications : exit app and restart it with the updates
## Legacy applciations 
Some applications were here before you arrived, they'll be here when you leave. Often no longer supported by the developper (ex: device ''too old", you're the support team. Document the system ! don't be afraid of the unknown, it may not be as bas as you think.  It vanbe quirky --> become the expert 


## Dependencies

