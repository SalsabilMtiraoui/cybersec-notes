How to make a change ? Upgrade a software, patch an application, change firewall configuration ect... A simple change can affect hundreds of people This is one of the most common risks in the enterprise, occurs very frequently. It's often overlooked. Need of clear policies (frequency, duration, installation process, rollback procedures) that are hard to implement (corporate culture)
Change approval process : formal process for managing change, avoid downtime, confusion and mistakes.
Typical approval proces : 
- complete the request form 
- Determine the purpose of the change 
- Identify the scope of the change (which system)
- Schedule date and time of the change
- Determine affected systems and the imapct of the change 
- Analyze the risk associated with the change
- Get end-user acceptane after the change is complete
## Ownership
 an individual or entity needs to make a change, they don't usually perform or own the actual change process. The owner manages the process,  process updates are provided to the owner and ensures the process is followed and acceptable. Address label printers needs to be upgraded : shipping and receiving department owns the process, IT handles the actual change.
Stakeholders : the people impacted by the change may have an input. This may not be as obvious as you might think, a single change can impact one individual or the whole company.

## Impact analysis 
Determine a risk value (high, medium, low). The risk can be minor, or far-reaching. the fix doesn't actually fix anything, it breaks something else, OS dailurs or data corruption. There is also risk of NOT doing the change : security vulnerability, application unvailibility, unexpected downtime...

## Test results
- Sandbox testing environments : no connection to the real world production, makes it possible to test in a safe space before. Test and confirm before deployement. Confirm the backout plan, a sandbox can't take everything into account.
## Backout plan 
If anything goes wrong, need a backup/backout plan. Revert back the changes should be possible, or go to something similar. some changes are really hard to revert, so need to find another way, have always good backups to get a good backout. 

## Maintenance window 
This might be the most difficult part of the process. During workday may affect production part. Overnights can be better, challenging for 24h/24h production environment, consider also the time of the year (holidays)

## SOP Standard Operating Procedure
change management is critical, affects everyone. The process mut be well documented, availible on the intranet along with standard processes and procedures. It's a living document.