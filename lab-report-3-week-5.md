# Lab Report 3

For this lab report, I decided to research the find command.



## Option 1: -iname

Previously in Week 4 lab, we saw the -name option for the find command. A problem with this command is that it is case sensitive. In the case that you are trying to perform a broader search(by not being case sensitive), you can use -iname.

Example 1:
```
[aganga@ieng6-201]:docsearch:81$ find technical/ -iname "legal*"
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
technical/government/Media/Legal-aid_chief.txt
technical/government/Media/Legal_Aid_Society.txt
technical/government/Media/Legal_Aid_attorney.txt
technical/government/Media/Legal_Aid_campaign.txt
technical/government/Media/Legal_Aid_in_Clay_County.txt
technical/government/Media/Legal_Aid_looks_to_legislators.txt
technical/government/Media/Legal_hotline.txt
technical/government/Media/Legal_services_for_poor.txt
technical/government/Media/Legal_system_fails_poor.txt
```
Here, I used the -iname option and searched "legal***" and as a result, all the .txt files starting with "legal"(not case sensitive) got displayed. Had I done this search using just -name "legal*", no results would have been displayed because all the .txt files starting with "legal" start with a capital L. The -iname option is also useful in the fact that if there were file names that started with "legal" and "Legal", using the -iname option once would have displayed all the files wheras if I used the -name option, I would have to call the find command twice, once for "legal" and another time for "Legal" to see the same results.


Example 2:
```
[aganga@ieng6-201]:docsearch:83$ find technical/ -iname "session*"
technical/government/Alcohol_Problems/Session2-PDF.txt
technical/government/Alcohol_Problems/Session3-PDF.txt
technical/government/Alcohol_Problems/Session4-PDF.txt
```
Here, I used the -iname option and searched "session*" and as a result, all the .txt files starting with "session"(not case sensitive) got displayed. Had I done this search using just -name "session*", no results would have been displayed because all the .txt files starting with "session" start with a capital S.

```
[aganga@ieng6-201]:docsearch:85$ find technical/ -iname "A*"
technical/biomed/ar104.txt
technical/biomed/ar118.txt
technical/biomed/ar120.txt
technical/biomed/ar130.txt
technical/biomed/ar140.txt
technical/biomed/ar149.txt
technical/biomed/ar297.txt
technical/biomed/ar309.txt
technical/biomed/ar319.txt
technical/biomed/ar321.txt
technical/biomed/ar328.txt
technical/biomed/ar331.txt
technical/biomed/ar383.txt
technical/biomed/ar387.txt
technical/biomed/ar407.txt
technical/biomed/ar408.txt
technical/biomed/ar409.txt
technical/biomed/ar422.txt
technical/biomed/ar429.txt
technical/biomed/ar430.txt
technical/biomed/ar601.txt
technical/biomed/ar612.txt
technical/biomed/ar615.txt
technical/biomed/ar619.txt
technical/biomed/ar624.txt
technical/biomed/ar68.txt
technical/biomed/ar745.txt
technical/biomed/ar750.txt
technical/biomed/ar774.txt
technical/biomed/ar778.txt
technical/biomed/ar79.txt
technical/biomed/ar792.txt
technical/biomed/ar795.txt
technical/biomed/ar799.txt
technical/biomed/ar93.txt
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen/atx1-6.txt
technical/government/Gen_Account_Office/ai00134.txt
technical/government/Gen_Account_Office/ai2132.txt
technical/government/Gen_Account_Office/ai9868.txt
technical/government/Media/AP_LawSchoolDebts.txt
technical/government/Media/A_Perk_of_Age.txt
technical/government/Media/A_helping_hand.txt
technical/government/Media/Abuse_penalties.txt
technical/government/Media/Advocate_for_Poor.txt
technical/government/Media/Aid_Gets_7_Million.txt
technical/government/Media/All_May_Have_Justice.txt
technical/government/Media/Annual_Fee.txt
technical/government/Media/Anthem_Payout.txt
technical/government/Media/Assuring_Underprivileged.txt
technical/government/Media/Attorney_gives_his_time.txt
technical/government/Media/Avoids_Budget_Cut.txt
technical/government/Media/agency_expands.txt
```
Here, I used the -iname option and searched "A*" and as a result, all the .txt files starting with upper and lower case "A" got displayed. The -iname, relative to the -name opttion is very useful in this case because all the files starting with "a" or "A" were displayed with one command wheras if I used the -name option, I would have to call the find command twice.



## Option 2: -mmin

The next option I will be discussing is -mmin option. This option is useful because it displays what files were modified X number of minutes ago. This is useful when you are working with many files(like we are dong in docsearch) and want to see what files were modified when.

Example 1:
```
[aganga@ieng6-201]:docsearch:95$ find -mmin -1
.
./new_file.txt
```
Here, I used the -mmin option and the -1 which means I am searching for files that were modified in the last minute. In the case of this example, I created a new file called new_file.txt and then ran the find command and as a result displayed the code block above because I created the new file and ran the command within a minute, thus giving the result above.


Example 2:
```
[aganga@ieng6-201]:docsearch:99$ find technical/government/About_LSC/ -mmin +10
technical/government/About_LSC/
technical/government/About_LSC/CONFIG_STANDARDS.txt
technical/government/About_LSC/Comments_on_semiannual.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
technical/government/About_LSC/Progress_report.txt
technical/government/About_LSC/Protocol_Regarding_Access.txt
technical/government/About_LSC/Special_report_to_congress.txt
technical/government/About_LSC/State_Planning_Report.txt
technical/government/About_LSC/State_Planning_Special_Report.txt
technical/government/About_LSC/Strategic_report.txt
technical/government/About_LSC/commission_report.txt
technical/government/About_LSC/conference_highlights.txt
technical/government/About_LSC/diversity_priorities.txt
technical/government/About_LSC/reporting_system.txt
```
Here, I used the -mmin option and +10 which means I am searching for files/directories(within technical/government/About_LSC/) that were modified more than 10 minutes ago. This as a result displayed all of the files in About_LSC because all of these files were "modified" when I originally cloned this repository to my VSCode and have remained unmodified since then.


Example 3:
```
[aganga@ieng6-201]:docsearch:90$ find -mmin -10
[aganga@ieng6-201]:docsearch:91$ 
```
Here, I waited a while and then used the -mmin option and the -10 which means I am searching for files that were modified in the last 10 minutes. For the case of this example, no files were displayed because I made sure to wait at least 10 minutes so that the file from example 1 that I created would not be displayed.



## Option 3: -size

The last option I will be discussing is -size option. This option is useful because it displays files based on a given size. This is especially useful when you are working with many files(like we are dong in docsearch) and want to see what files are taking up how much/majority of the storage.

Example 1:
```
[aganga@ieng6-201]:docsearch:109$ find technical/ -size +200
technical/911report/chapter-1.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-3.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/biomed/1471-2105-3-2.txt
technical/government/About_LSC/State_Planning_Report.txt
technical/government/About_LSC/commission_report.txt
technical/government/Env_Prot_Agen/bill.txt
technical/government/Env_Prot_Agen/ctm4-10.txt
technical/government/Env_Prot_Agen/multi102902.txt
technical/government/Env_Prot_Agen/tech_adden.txt
technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
technical/government/Gen_Account_Office/May1998_ai98068.txt
technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
technical/government/Gen_Account_Office/ai9868.txt
technical/government/Gen_Account_Office/d01376g.txt
technical/government/Gen_Account_Office/d01591sp.txt
technical/government/Gen_Account_Office/d0269g.txt
technical/government/Gen_Account_Office/d02701.txt
technical/government/Gen_Account_Office/gg96118.txt
technical/government/Gen_Account_Office/im814.txt
technical/government/Gen_Account_Office/pe1019.txt
```
Here, I used the -size option and +200 which displays all files in technical/ that are more than 200 bytes of storage, thus explaining the display above. This is useful as if I was worried about storage, I can now see the .txt files that are taking up the most relative space.


Example 2:
```
[aganga@ieng6-201]:docsearch:110$ find -size +5M
./.git/objects/pack/pack-76c2be97747be8c169abcc0a0a6082bddbd7ec39.pack
./docsearch/.git/objects/pack/pack-b18429902f8e5328cd035841e8df94542e262a90.pack
```
Here, I used the -size option and +5M which displays anything that is more than 5 megabytes of storage, thus explaining the display above. This is useful because now I can see exactly is taking 5 or more megabytes or storage if I was worried about storage.


Example 3:
```
[aganga@ieng6-201]:docsearch:113$ find technical -size -10
technical
technical/911report
technical/government
technical/government/About_LSC
technical/government/Alcohol_Problems
technical/government/Env_Prot_Agen
technical/government/Gen_Account_Office/d01121g.txt
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/AP_LawSchoolDebts.txt
technical/government/Media/A_Perk_of_Age.txt
technical/government/Media/Advocate_for_Poor.txt
technical/government/Media/Aid_Gets_7_Million.txt
technical/government/Media/All_May_Have_Justice.txt
technical/government/Media/Attorney_gives_his_time.txt
technical/government/Media/Barnes_Volunteers.txt
technical/government/Media/Barnes_new_job.txt
technical/government/Media/Barnes_pro_bono.txt
technical/government/Media/Barr_sharpening_ax.txt
technical/government/Media/Bias_on_the_Job.txt
technical/government/Media/Boone_legal_service.txt
technical/government/Media/BusinessWire2.txt
technical/government/Media/Butler_Co_attorneys.txt
technical/government/Media/Campaign_Pays.txt
technical/government/Media/Civil_Matters.txt
technical/government/Media/Commercial_Appeal.txt
technical/government/Media/Court_Keeps_Judge_From.txt
technical/government/Media/Crains_New_York_Business.txt
technical/government/Media/Disaster_center.txt
technical/government/Media/Do-it-yourself_divorce.txt
technical/government/Media/Domestic_violence_aid.txt
technical/government/Media/Donald_Hilliker.txt
technical/government/Media/Entities_Merge.txt
technical/government/Media/Eviction_law.txt
technical/government/Media/FY_04_Budget_Outlook.txt
technical/government/Media/Federal_agency.txt
technical/government/Media/Fire_Victims_Sue.txt
technical/government/Media/Firm_to_the_Poor_Needs_Help.txt
technical/government/Media/FortWorthStarTelegram.txt
technical/government/Media/Free_legal_service.txt
technical/government/Media/Funding_May_Limit.txt
technical/government/Media/Funding_cuts_force.txt
technical/government/Media/Funds_Shortage.txt
technical/government/Media/Ginny_Kilgore.txt
technical/government/Media/Hard_to_Get.txt
technical/government/Media/Helping_Hands.txt
technical/government/Media/Higher_Registration_Fees.txt
technical/government/Media/Higher_court.txt
technical/government/Media/It_Pays_to_Know.txt
technical/government/Media/Justice_requests.txt
technical/government/Media/Kiosks_for_court_forms.txt
technical/government/Media/Law-school_grads.txt
technical/government/Media/Law_Award_from_College.txt
technical/government/Media/Lawyer_Web_Survey.txt
technical/government/Media/Legal_Aid_Society.txt
technical/government/Media/Legal_Aid_attorney.txt
technical/government/Media/Legal_Aid_campaign.txt
technical/government/Media/Legal_Aid_in_Clay_County.txt
technical/government/Media/Legal_Aid_looks_to_legislators.txt
technical/government/Media/Legal_hotline.txt
technical/government/Media/Legal_services_for_poor.txt
technical/government/Media/Lindsays_legacy.txt
technical/government/Media/Lockyer_Warns.txt
technical/government/Media/Low-income_children.txt
technical/government/Media/New_Online_Resources.txt
technical/government/Media/New_funding_sources.txt
technical/government/Media/Nonprofit_Buys.txt
technical/government/Media/Oregon_Poor.txt
technical/government/Media/Owning_a_Piece.txt
technical/government/Media/Paralegal_Honored.txt
technical/government/Media/Philly_Lawyers.txt
technical/government/Media/Poor_Lacking_Legal_Aid.txt
technical/government/Media/Pro-bono_road_show.txt
technical/government/Media/Pro_Bono_Services.txt
technical/government/Media/Program_Lodges.txt
technical/government/Media/Providing_Legal_Aid.txt
technical/government/Media/Rental_rules.txt
technical/government/Media/RoanokeTimes.txt
technical/government/Media/Rumble_in_the_Bronx.txt
technical/government/Media/Self-Help_Website.txt
technical/government/Media/State_funding.txt
technical/government/Media/Supporting_Legal_Center.txt
technical/government/Media/Texas_Supreme_Court.txt
technical/government/Media/The_Bend_Bulletin.txt
technical/government/Media/The_Columbian.txt
technical/government/Media/Towson_Attorney.txt
technical/government/Media/Valley_Needing_Legal_Services.txt
technical/government/Media/Volunteers_Step_Up.txt
technical/government/Media/Wilmington_lawyer.txt
technical/government/Media/Wingates_winds.txt
technical/government/Media/Workers_aid_center.txt
technical/government/Media/agency_expands.txt
technical/government/Media/balance_scales_of_justice.txt
technical/government/Media/defend_yourself.txt
technical/government/Media/families_saved.txt
technical/government/Media/fight_domestic_abuse.txt
technical/government/Media/help_rent-to-own_tenants.txt
technical/government/Media/highlight_Senior_Day.txt
technical/government/Media/less_legal_aid.txt
technical/government/Media/not_accessible_to_disabled.txt
technical/government/Media/pro_bono_efforts.txt
technical/government/Media/residents_sue_city.txt
technical/government/Media/water_fees.txt
technical/government/Post_Rate_Comm
technical/plos/pmed.0010023.txt
technical/plos/pmed.0010024.txt
technical/plos/pmed.0010025.txt
technical/plos/pmed.0010029.txt
technical/plos/pmed.0010030.txt
technical/plos/pmed.0010047.txt
technical/plos/pmed.0010048.txt
technical/plos/pmed.0010049.txt
technical/plos/pmed.0010050.txt
technical/plos/pmed.0010067.txt
technical/plos/pmed.0010068.txt
technical/plos/pmed.0010069.txt
technical/plos/pmed.0010070.txt
technical/plos/pmed.0020019.txt
technical/plos/pmed.0020020.txt
technical/plos/pmed.0020021.txt
technical/plos/pmed.0020022.txt
technical/plos/pmed.0020023.txt
technical/plos/pmed.0020024.txt
technical/plos/pmed.0020027.txt
technical/plos/pmed.0020028.txt
technical/plos/pmed.0020047.txt
technical/plos/pmed.0020048.txt
technical/plos/pmed.0020065.txt
technical/plos/pmed.0020074.txt
technical/plos/pmed.0020082.txt
technical/plos/pmed.0020085.txt
technical/plos/pmed.0020086.txt
technical/plos/pmed.0020090.txt
technical/plos/pmed.0020091.txt
technical/plos/pmed.0020094.txt
technical/plos/pmed.0020113.txt
technical/plos/pmed.0020114.txt
technical/plos/pmed.0020115.txt
technical/plos/pmed.0020116.txt
technical/plos/pmed.0020117.txt
technical/plos/pmed.0020120.txt
technical/plos/pmed.0020145.txt
technical/plos/pmed.0020146.txt
technical/plos/pmed.0020148.txt
technical/plos/pmed.0020149.txt
technical/plos/pmed.0020150.txt
technical/plos/pmed.0020157.txt
technical/plos/pmed.0020189.txt
technical/plos/pmed.0020191.txt
technical/plos/pmed.0020192.txt
technical/plos/pmed.0020195.txt
technical/plos/pmed.0020196.txt
technical/plos/pmed.0020198.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020201.txt
technical/plos/pmed.0020226.txt
technical/plos/pmed.0020237.txt
technical/plos/pmed.0020238.txt
technical/plos/pmed.0020258.txt
technical/plos/pmed.0020268.txt
technical/plos/pmed.0020273.txt
technical/plos/pmed.0020274.txt
technical/plos/pmed.0020275.txt
technical/plos/pmed.0020278.txt
technical/plos/pmed.0020281.txt
```
Here, I used the -size option and -10 which displays anything that is less than 10 bytes of storage, thus explaining the display above. This is useful because now I can see the files that have the least relative impact in terms of using storage space.









