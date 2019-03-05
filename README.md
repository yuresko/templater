# Jamf Pro Templater

The Jamf Pro Templater gives a Jamf Pro admin the ability to autopopulate their environment with various workflows and templates!

*NOTE: Be advised that due to environmental differences, as always, it is best to test in your dev/eval server before deploying in production.*

## What is it?

A single-click solution for the creation of workflows! Using your Jamf Pro API credentials, the Jamf Pro Templater will take tested and up-to-date workflows stored on a server, and populate all items necessary for the specified workflow in your Jamf Pro! Templates can deploy workflows as basic as adding a Smart Group looking for Computers that have not checked in for 14 Days, or as complex as a full CIS workflow including benchmarks, remediation and reporting.  One click can save you hours of work and testing (and human error), so why reinvent the wheel?!

## How it works?

Exports of workflows are taken from working production enviornments, scrubbed for credentials/company specific information, and stored on a server. Once these workflows are tested, they are offered and are able to populate your Jamf Pro via https://templater.jamfpro.services. Jamf Pro Templater uses GET, POST and PUT in order to properly apply the templates. Just like any secure server, log out when you're finished using your session of Jamf Pro Templater (found at the bottom of each page). 
*NOTE: Policies are marked as "disabled" and there are no device specific information passed in any of the workflows.
NOTE: Your Jamf Pro server must be able to access AWS.*

## How do I use it?
1. Log in using your Jamf Pro credentials.
2. Click the options on the left hand side to enter the category of templates...
 - Computer Templates: Computer-based workflows (Select as many you'd like at once!)
 - Mobile Device Templates: iOS/tvOS based workflows (Select as many you'd like at once!)
 - Industry Templates: Full Jamf Pro templates (Select only one at a time. To only be used on new instances for demos or testing)
 - Custom Upload: Upload .zip exports of templates...p2p, JamfNation, Jamf Support, Jamf Blog etc.
3. Select desired templates/workflows, and click Go!
4. Wait for a Success/complete page.

*NOTE: DO NOT refresh your page while Jamf Pro Templater is working, the upload may error out*

## What does it populate?

All necessary Jamf Pro options for workflow to work (in this order)...
- sites
- jamfusers
- jamfgroups
- buildings
- categories
- departments
- distributionpoints
- ldapservers
- networksegments
- netbootservers
- softwareupdateservers
- dockitems
- printers
- computerextensionattributes
- mobiledeviceextensionattributes
- userextensionattributes
- directorybindings
- packages
- scripts
- mobiledeviceapplicationsicon
- selfservicepolicyicon
- macapplications
- mobiledeviceapplications
- computers
- mobiledevices
- users
- staticcomputergroups
- staticiosgroups
- staticusergroups
- smartcomputergroups
- smartiosgroups
- smartusergroups
- patchpolicies
- restrictedsoftware
- mobiledeviceconfigurationprofiles
- advancedcomputersearches
- advancedmobiledevicesearches
- osxconfigurationprofiles
- policies

## Success/Errors

Upon completion, you will be shown either with a "Success" page or a "Completed, with errors" page. "Success" means there were no errors in upload, no duplicates found and all files were uploaded properly. "Completed, with errors" means there may be duplicates found on the server with same name in which case verify on the Jamf Pro server that variables in the duplicates are the same as in the template. If different, apply the template again after adjusting name of item to be added! There are a few check-fails in place to ensure best possible upload, but, due to varying enviornments (and that this should be executed first in a dev/test/eval Jamf Pro), verify errors found in Jamf Pro to rule out false-negatives!


