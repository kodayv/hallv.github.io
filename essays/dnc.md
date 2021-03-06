---
layout: essay
type: essay
title: The Democratic National Committee Cyber-attacks
date: 2017-05-10
labels:
  - DNC
  - Cyber-attack
  - FancyBear
  - CozyBear
---

In April 2016 the Democratic National Committee (DNC) contacted American cybersecurity company CrowdStrike to investigate a suspected breach within their network (CrowdStrike 2016). The security company discovered two separate cyber attackers; ‘CozyBear and ‘FancyBear’. Both of these attackers have since been identified as part of separate Advanced Persistent Threats (APT), and perceived as “Russian state-sponsored actors” (Bencha 2016). This essay will explain the evidence collected on these attacks which identified them to their respective APTs, and links which connect the APTs to a government sponsored organization within Russia. 

## FANCY BEAR
<img class="ui medium left circular floated image" src="https://www.crowdstrike.com/blog/wp-content/uploads/2016/09/FancyBearBlog.jpg">
### Overview of the Attack

FancyBear operated by handpicking targets within the DNC, acquired IP addresses to scan and prioritize, and then attacked by sending scam emails directed to a fake website that downloaded a file dropper while the victim was observing the webpage (Bencha 2016). Once the DNC network was exploited, stage one of the installation process began with a file executing X-Agent; a toolset with the capability to commit remote commands, transmit files to another server, key-log, and connect the network to the attackers’ command and control center (C&C) (CrowdStrike 2016).

Once connected, an additional dropper wrote a Dynamic Link Library (DDL) component and configuration file known as X-Tunnel, which established additional connections to 3 different servers (Bencha 2016). This tool allowed all data transmissions to be obscured from public view with the use of Network Address Translation (NAT) while it executed commands by remote (CrowdStrike 2016). X-Agent and X-Tunnel are potent tools as they periodically clean log files and reset timestamps, and these tool enable the hackers to execute modules, upload and download files, and deploy through an open-source GitHub program called RemCom (Bencha 2016).

The CrowdStrike official report identified that FancyBear had “performed credential dumping, reconnaissance, remote command execution, exfiltration staging, keylogging and lateral movement when accessing a key shared drive within the DNC network” ( pg11). It was able to rob the DNC of the current research on all opposing Republican candidates during the few days it had infiltrated the system (CrowdStrike 2016).
<img class="ui medium right floated image" src="http://lofrev.net/wp-content/photos/2016/10/crowd_strike_1.png">

### Identification features

FancyBear’s use of the X-Agent and X-Tunnel tools links this attack with a group known as Sofacy. Being documented in attacks since 2014, Sofacy has targeted political and military systems including telecommunication services, aerospace, and cyber-crime services in Ukraine, Spain, Romania, United States, and Canada (Bencha 2016). Due to its targeting groups, length in which this group has been infiltrating systems, and ability to infiltrate into various applications, the group associated with these attacks have been named APT28. BitDefender analyzed the compilation times of the binaries in files associated with APT28, and discovered that the 88% of the compilations occurred Monday-Friday, 8am to 6pm in UTC +4 (Bencha 2016). The countries in this time zone include Azerbaijan, Georgia, and part of Russia. The Russian part includes St. Petersburg and Moscow, and has been UTC +4 year round since 2014 (Machov 2014). Additionally, a file was found that had its header written in Russian. Of the countries that have Russian speakers and fall in UTC +4, Russia is the only one known to have all the resources necessary to fund these skilled (Bencha 2016)
<img class="ui medium left floated image" src="https://c.tadst.com/gfx/750x500/timezone-map5.png?1">
 
 With the evidence gathered suggesting Russia, more new information came in from an external entity. Further investigation revealed that the C&C server’s domain for this particular attack was registered to Frank Merdeux residing in France (ThreatConnect 2016). In July 2016, following the release of CrowdStrike’s report, a blog by ‘Guccier2.0’ made the declaration that he, a Romanian anti-government hacker, independently conducted the FancyBear attack (Collier 2016). An analysis of his Twitter posts and America Online email correspondence to journalists easily revealed a geolocation reference to France; which is suspicious due to the anonymous nature of elite hackers. Although Goccier2.0 claimed to not speak Russian, the Virtual Private Network (VPN) used by him to communicate with journalists was a site completely written in Russian called Elite VPN (ThreatConnect 2016). When the hacker spoke to journalists in Romanian, his grammar structure resembled that of an Eastern Slavic language instead of a native Romanian structure (Collier 2016).  To prove that he was the hacker, he posted some of the documents stolen from the DNC. Information on the documents history show that the last person to save the file was ‘Felix Dzerzhinsky’ (written in Russian Cyrillic) (Collier 2016). In light of this evidence it has been concluded by security company ThreatConnect that Guccier2.0 is a person or group of people from Russia who used France as a fronted location (ThreatConnect 2016). CrowdStrike stands by its initial conclusion that FancyBear is part of APT28.
 
## COZY BEAR	
<img class="ui medium right circular floated image" src="https://www.crowdstrike.com/blog/wp-content/uploads/2016/09/cozy-bear.jpeg">

### Overview of the attack

CozyBear is believed to have been installed in a two-stage process. By the time CrowdStrike began their investigation into the attack, stage two of the implant was underway, and the initial installation of the criminal software was not found (CrowdStrike 2016). F-Secure systems published that CozyBear, also called CozyDuke, CozyCar, Cozer, and EuroAPT, primarily enters a network by the means of an email linking to a website hosting a ZIP file (Lehtio 2015a). This dropper file is hidden with an image or pdf decoy that will install CozyBear components and files while the victim is looking at the decoy attachment.
 
 The second stage of the installation, the establishment of a backdoor, was discovered during CrowdStrike’s investigation with the attackers utilizing Windows Management Instrumentation (WMI) (CrowdStrike 2016). The WMI is a very potent tool that hackers can use, due to its vast amount of events, objects, and methods that have been installed on all Widows operating systems since 1998 (Graeber 2015). Additionally, CozyBear implemented a second, Python language based, backdoor program known as ‘SeaDaddy’ (CrowdStrike 2015). SeaDaddy, also referred to as SeaDuke and SeaDask, has the ability to upload and download files, and self-delete traces of malware from the infected system (Symantic 2015). Investigators observed that SeaDaddy was used to implant PowerShell; a scripting language that has great synergy with WMI (Graeber 2015). Together WMI and PowerShell were able to gain access the DNC network, and during its almost entire year inside the system, collected various communications intelligence data (CrowdStrike 2016). 

### Identification features
<img class="ui medium left floated image" src="https://cdn.securelist.com/files/2015/04/onion.png">


CozyBear had been observed to connect with the C&C server Nostressjob.com, whose domain, and registered name John Kasai, is associated with malware tools ‘MiniDuke’ and ‘OnionDuke’ (Lehtio 2015a). CozyBear also utilized the same DLL names for files and exports, and the same encryption algorithm for the DLL strings that the OnionDuke used (Lehtio 2015a). With this information F-Secure renamed the CozyBear program ‘CozyDuke’, to signify its connection to the ‘Duke’ set of malware tools. 

Since the identification of the Dukes in 2008, it has targeted various political and military establishments to include embassies, senates, parliaments, ministries of defense and of foreign affairs, political organizations, defense contractors, Chechen extremist organizations, and Russian drug lords (Lehtio 2015b). The group running the Dukes appear to have a stable source of funding due to its longevity, constant revisions, and propensity to modify an identified attack to regain stealth over retraction (Lehtio 2015b). The group is also well organized, and has attacked a high-profile target simultaneously while attacking smaller targets. Due to its long duration, persistence in obtaining intelligence, and its targets, the operators of the Dukes are referred to as APT29. 

In order to track the attackers, all programs associated with APT29 were analyzed. When PinchDuke, the first identified APT29 program, came out, a Russian error message was found in several samples of the malware (Lehtio 2015b). By compiling all the timestamps found when the GeminiDuke trafficked data from 2009 to 2013, it was discovered that the high periods of activity were Monday thru Friday, 6am to 4pm UTC+0 with daylight savings time adjustments (Lehtio 2015b). When adjusted to normal working hours, UTC+3 in the summer and UTC+4 in the winter would have the time range between 9am and 7pm. This area corresponds to several regions including Belarus, Ukraine, Turkey, and the Russian areas holding St. Petersburg and Moscow (TimeandDate 2017). While Russia stopped having a daylight savings change in 2011 by order of Russian President Vladimir Putin to leave the Moscow region as UTC +3 year round, the timestamps from the GeminiDuke activities after 2011 still reflected the daylight savings time changes (Lehtio 2015b). Although cyber-security company F-Secure published in its official report that the hackers in Russia “failed to update the computer they were using to compile GeminiDuke samples, so that the timestamps seen in later samples still appear to follow the old definition of Moscow Standard”, it fails to explain the change in activity times that would have ensued; the timestamp should have shown activity of UTC +3 in the summer of 2012 from 9am to 7pm, and UTC +4 in the winter from 10am to 8pm, unless the workers themselves observed daylight savings time outside of Putin’s orders (p 17).
	
<img class="ui medium left floated image" src="https://www.crowdstrike.com/blog/wp-content/uploads/2016/09/cozy-bear-.jpg">

## Conclusion

The cybersecurity firms F-secure Labs, ThreatConnection, Bitdefender, and Symantec have all agreed with CrowdStrike’s conclusion that both CozyBear and FancyBear attacks came from APT groups believed to be working from Russia. Their tool sets are complex which demonstrates constant funding and security, their attacking campaigns long, and their services beneficial to government institutions. This evidence uncovered on the FancyBear and CozyBear attacks was sufficient enough for former President Obama to publicly apply sanctions to suspected individuals, diplomats, and associated companies in December 2016 (Perez & Diaz 2017).However, there is also the chance that given the advances in technology, the clues that were revealed may be purposefully misleading (Bencha 2016). APT groups have been constantly finding new means of stealth to include resetting the timestamps and removing their native language from the files, so finding evidence to the responsible party is becoming harder, while the number of attacks identified from APT groups have been increasing (Lehtio 2015b). 

<img class="ui large centered image" src="https://upload.wikimedia.org/wikipedia/commons/1/1c/APT28_APT29_Techniques_-_Spearphising.png">


<hr><hr>

## Works Cited
Bencha, R., Valamanu, C., Maximciuc, A., & Luncasu, V. (2016) APT28 Under the Scope: A Journey into Exfiltrating Intelligence and Government Information. Bitdefender. Retrieved from https://download.bitdefender.com/resources/media/materials/white-papers/en/Bitdefender_In-depth_analysis_of_APT28%E2%80%93The_Political_Cyber-Espionage.pdf

Collier, Kevin (Jul 26 2016). Guccifer 2.0 Is Likely A Russian Begging Us To Write About DNC Hack. Vocativ. Retrieved from http://www.vocativ.com/343010/guccifer-2-0-dnc-hack/

CrowdStrike (2016). Cyber Intrustion Services Casebook 2016. Retrieved from https://go.crowdstrike.com/rs/281-OBQ-266/images/Report2016CyberIntrusionServicesCasebook.pdf?aliId=6827661

Graeber, Matt (2015). Abusing Windows Management Instrumentation (WMI) to Build a Persistent, Asyncronous, and Fileless Backdoor. Black Hat 2015. Retrieved from https://www.blackhat.com/docs/us-15/materials/us-15-Graeber-Abusing-Windows-Management-Instrumentation-WMI-To-Build-A-Persistent%20Asynchronous-And-Fileless-Backdoor-wp.pdf

Lehtio, Artturi (Apr 22 2015a); CozyDuke. F-Secure Labs. Retrieved from https://www.f-secure.com/documents/996508/1030745/CozyDuke
	
Lehtio, Artturi (Sep 17 2015b). The Dukes: 7 Years Of Russian Cyber-Espionage. F-Secure. Retrieved from https://www.f-secure.com/documents/996508/1030745/dukes_whitepaper.pdf

Machov, Yuri (Jul 22 2014). Rossiyanam vernuli zimneye vremya [Russians have returned to winter time].  TASS. Retrieved from http://tass.ru/obschestvo/1333711
	
Perez, Evan & Diaz, Daniella (Jan 2 2017). White House announces retaliation against Russia: Sanctions, ejecting diplomats. CNN. Retrieved from http://www.cnn.com/2016/12/29/politics/russia-sanctions-announced-by-white-house/

Symantec (Jul 15 2015) “Forkmeiamfamous”: Seaduke, latest weapon in the Duke armory. Retrieved from  http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weaponduke-armory2.JoshGrunzweig

ThreatConnect (June 17 2016). Rebooting Watergate: Tapping into the Democratic National Committee. Retrieved from https://www.threatconnect.com/blog/tapping-into-democratic-national-committee/	

TimeandDate (2017). Time Zone Map. Retrieved from https://www.timeanddate.com/time/map/ 
