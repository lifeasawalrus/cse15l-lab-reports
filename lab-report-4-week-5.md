# Lab Report 4

The following are 3 examples of three different command-line options of "grep."

First, let's check out grep's `-i` option:
```
grep -i john technical/government/Post_Rate_Comm/*
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:John Waller
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:Jöelle Toledano, John Waller, and Spyros Xenakis. 2002. "Delivery
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:Cohen, Robert, William Ferguson, John Waller and Spyros Xenakis.
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:Scarfiglieri, Vincenzo Visco Comandini, John Waller and Spyros
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:Robert H. Cohen William W. Ferguson John D. Waller Spyros S.
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:John Waller
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:Cohen, Robert, William Ferguson, John Waller, and Spyros
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:Scarfiglieri, Vincenzo Visco Comandini, John Waller and Spyros
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:Dr. John Haldi has brought to our attention that the daily
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:John Panzar has characterized street delivery as a bottleneck
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:Panzar, John, "Competition, Efficiency, and the Vertical
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Matthew Robinson John Waller
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Samuel Johnson said Patriotism is the last refuge of a scoundrel
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:it has been difficult to quantify. We agree with John Panzar (2001)
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Cohen, Robert H., William W. Ferguson, John D. Waller, and
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Cohen, Robert H., William W. Ferguson, John D. Waller, and
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Cohen, Robert H., William W. Ferguson, John D. Waller and Spyros
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:Panzar, John C. 2001. "Funding Universal Service Obligations:
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt:admiration for Representative John McHugh and his staff. In the
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:John Nolan and I were talking about some of his
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:John. Turns out that Bill got one letter last year that just tore
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:this year, and the letter wound up in John's in box. He shared a
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:Cohen, Robert H., William W. Ferguson, John D. Waller, and
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:Haldi, John and John T. Schmidt, 1999, "Transaction Costs of
```
`-i` shows results for the argument passed to grep, ignoring the case of each letter. So although I passed "john" it showed results for all instances of "John." This is especially helpful if you wanted to include every instance of your argument in the results, since captialized words that appeared at the beginning of a sentence would not be included without `-i`.

Notice that it showed each instance of "John" in context, presenting the path to the file each time. Let's clean up the output a bit by including the `-c` option.
```
grep -i -c john technical/government/Post_Rate_Comm/*
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:4
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:1
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:3
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:1
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:2
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:7
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt:1
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:3
technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt:0
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:2
technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt:0
technical/government/Post_Rate_Comm/Redacted_Study.txt:0
technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt:0
technical/government/Post_Rate_Comm/WolakSpeech_usps.txt:0
```
`-c` constricts the output of grep to just give the *count* of the argument passed to it, without spamming context or printing the file-path multiple times. This option is useful if you are trying to quickly and easily find out the number of instances a word appears in a directory.

`-n` is another helpful command:
```
rep -i -o -n john technical/government/Post_Rate_Comm/*
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:20:John
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:451:John
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:454:John
technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:460:John
technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:14:John
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:16:John
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:651:John
technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:656:John
technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:482:John
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:132:John
technical/government/Post_Rate_Comm/Cohenetal_Scale.txt:156:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:14:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:20:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:31:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:803:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:809:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:813:John
technical/government/Post_Rate_Comm/Cohenetal_comparison.txt:835:John
technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt:188:John
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:575:John
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:579:John
technical/government/Post_Rate_Comm/Gleiman_gca2000.txt:586:John
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:785:John
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:795:John
technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt:795:John
```
`-n` prints the *line number* that the argument was found on in the file. This is particularly helpful if you are searching code files for specific functions and want to find what line they are located on. (`-o` was used to reduce output of context to just the argument word)

Let's see a few more examples of these three options in action.
```
grep -i criticized technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/Session4-PDF.txt:Gentilello clarified that he had not criticized the peer-review
```
```
grep -i -n "every time" technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:140:"referral" could be included every time, but acknowledged that it
```
```
grep -i -c for technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:95
technical/government/Alcohol_Problems/Session2-PDF.txt:108
technical/government/Alcohol_Problems/Session3-PDF.txt:212
technical/government/Alcohol_Problems/Session4-PDF.txt:210
```
```
grep -c for technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:93
technical/government/Alcohol_Problems/Session2-PDF.txt:103
technical/government/Alcohol_Problems/Session3-PDF.txt:208
technical/government/Alcohol_Problems/Session4-PDF.txt:201
```
```
grep -n Please technical/government/Gen_Account_Office/*
technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt:174:diskette (in Word or ASCII format). Please send any mail to the
technical/government/Gen_Account_Office/June30-2000_gg00135r.txt:920:Please contact me or Curtis Copeland at (202) 5128676 if you or
technical/government/Gen_Account_Office/d01121g.txt:98:improving the guide. Please submit updates and suggestions on how
```
```
grep -i -n "Please do" technical/government/Gen_Account_Office/*
technical/government/Gen_Account_Office/Letter_WalkerJan30-2001.txt:131:questions, comments or concerns, please do not hesitate to contact
technical/government/Gen_Account_Office/pe1019.txt:300:that you try this out yourself, so please do it before
```
format