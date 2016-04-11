---
title: Folder Structure
---

Proposal folders are organized as follows ("#=>" is a comment):

<pre>
Proposals/
  [Opportunity Name]/          #=> (see note below)
    00_Background/             #=> contains assorted research documents
    10_Teaming/
      NDAs/
      TAs/
    [Specific Procurement]/    #=> example names: "RFP_2015_10_15", "RFI_2015_05_05"
      20_From_Government/      #=> contains procurement docs issued by government
      50_Pricing/              #=> pricing source files
        Team_Input/
          SubA/                #=> can be shared w/ subs individually for input, data calls, collaboration
          SubB/
          ...
      70_Drafts/
        Pink/
          Pink_Ready/         #=> drafts go here when ready for review
          Pink_Reviewed/      #=> reviewers place commented docs here
        Red/
        Gold/
      75_Graphics/
        Ready/                #=> drafts from authors
          Archive/
        Converted/            #=> "pretty" graphics from graphics SME
      90_Final_Submission_[DATE]/
        Source_Files/         #=> source text (ms word, excel, etc.) and graphics (ppt, vsd, psd, etc.)
        As_Submitted/         #=> exact files submitted to government
      9*_[Followup Submission Name]_[Date]/
</pre>

Notes:

  * [DATE] is in YYYY_MM_DD format (e.g. "2013_12_25")
  * Organization under Proposals/[Opportunity Name] can be multiple levels. Target customers would have a dedicated folder, and probably subfolders for major initiatives (FDIC/ITAS-II, FDIC/Outsourcing). Others would be simply by agency or agency group (Defense).