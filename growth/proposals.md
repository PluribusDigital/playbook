# Proposal Guide

This guide allows Pluribus staff and teaming partners to be synced on what to expect when creating a proposal together.

## Writing Style

> (i) Never use a metaphor, simile, or other figure of speech which you are used to seeing in print.
> 
> (ii) Never use a long word where a short one will do.
> 
> (iii) If it is possible to cut a word out, always cut it out.
> 
> (iv) Never use the passive where you can use the active.
> 
> (v) Never use a foreign phrase, a scientific word, or a jargon word if you can think of an everyday English equivalent.
> 
> (vi) Break any of these rules sooner than say anything outright barbarous.
> 
> *― George Orwell, Politics and the English Language*

### General

 * _Short paragraphs:_ If a paragraph is longer than 5 lines, there should be a good reason why. Is it really 2 ideas (thus 2 paragraphs)? Should some bulk of content be broken into bullets?
 * _Use subheadings:_  Some form of subheading should group each 1-3 paragraphs. A half page or more of unbroken text is an issue.
 * _Use bullets:_ Break large paragraphs into bullets.

### Specific Rules

| Rule | Bad Example(s) | Good Example(s) |
| --- | --- | --- |
| Direct phrasing | Pluribus will work to... <br> Pluribus intends to... <br>We understand that some PMM type deliverables are more applicable... | Pluribus will... <br> Some PMM deliverables are more applicable... |
| Present tense | The PM will then update the plan...<br>Pluribus will deliver per agile methodology... | The PM updates the plan...<br>Pluribus delivers per agile methodology... |
| Active voice | Artifacts are created... | Analysts create artifacts |
| Plain language | With a high multitude of documents and artifacts available... | With many artifacts available... [see also](https://xkcd.com/1133/) |

Notes:

 * Past tense is appropriate for experience citations, since the activity did occur in the past

## Document Formatting

We use MS Word to author proposals. Some rules on formatting options and gotcha's.

 * Left align text, do not justify
 * Do not use Word's hyphenation feature globally (only sparingly in specific blocks of text to fine-tune page layout)
 * Do not use Word's "insert->reference" feature for auto cross-referencing sections/figures/tables
    - Instead, use reference in draft along the lines of "Figure XXX"
    - Hard code figure numbers for final drafts
    - (Yes, it's a pain to manually update, but the alternative is far more dangerous!)
 * Do not manually format text. Do use built-in styles, primarily:
    - Normal
    - Headings (1-4)
    - Subheading
    - Body Bullet
    - Caption
    - Table Text (within a table, obviously)
    - Table Bullet (within a table, obviously)

## Reviews

### General Review Guidance

 * _Be specific_: Provide very specific, actionable feedback. General feedback ("it's good", "needs work") doesn't help.
 * _Suggest_: Either suggest a specific fix ("Please substantiate this claim - perhaps citing how we configured Documentum at EPA"); or at least a specific direction to fix ("Please substnatiate, ideally citing another Documentum experience at a past project.")
 * _Be candid_: We would rather hear about problems from our reviewers, than in a loss debrief. Snark in comments doesn't help, but direct, critical, candid feedback is always welcome.
 * _Include the Good_: Cite specific positive feedback for important well-done points ("This point really hits home and makes our approach seem real and practical", "This graphic really boils down the approach well and makes it easy to understand") so that authors don't edit out anything good when correcting the bad.

### "Color Team" Reviews

Pluribus is less formal than most. We typically perform only Red and Gold reviews. 

#### Pink Team (Storyboard)

__Objective__: Make sure the draft is going in the right direction.

__Draft Expectation__: (To be refined by Proposal Manager) 

 * A complete outline with a clear place to address any compliance item in the instructions
 * Initial key graphics, text blurbs, or raw bullets of content to convey the gist of important or complex sections
 * Grammar errors, etc., are fine

__Review For__:
 
 * Compliance: Is there is a clear home for all necessary content?
 * Substance: Are sections with partial content/graphics going in the right direction? 
 * Outline Flow: Is the outline logical and likely to flow well from one section to another?
 * _NOT: editorial, writing flow, grammar, spelling_

#### Red Team (Compliance)

__Objective__: Make sure the draft is complete and compliant.

__Draft Expectation__:  

 * A complete draft, with decent quality text in each section
 * Good draft graphics and tables (may not be in "pretty" form yet)
 * Sections should flow well, but may have some rough edges

__Review For__:
 
 * Compliance: Is the draft compliant - contains all required content?
 * Substance: Does the content make sense? Is it accurate?
 * Flow: Do sections fit together in a logical order and flow from one to the next?
 * Win (secondary): In compliant sections, how well will it score? How can we increase the score?
 * Editorial (secondary): Focus on substantive mistakes (wrong client name), not minor style edits.
 * _NOT: detailed editorial and spelling_

#### Gold Team (Win)

__Objective__: Make the draft stand apart in the evaluation process.

__Draft Expectation__:  

 * A complete, winning draft, with high quality text in each section
 * Win themes come through as part of a compelling story
 * Fully compliant
 * Final-form graphics and tables
 * Sections flow well

__Review For__:
 
 * Win: How well will it score? How can we increase the score?
 * Compliance: Is any compliance in doubt?
 * Substance: Does the content make sense? Is it accurate?
 * Flow: Do sections fit together in a logical order and flow from one to the next?
 * Editorial: Is it well written and meets the style guide?

### Workflow

 1. __Author__ creates a draft, optionally saving in the `70_Drafts/[color]` folder while working.
 2. When the draft is ready for review, __Author__ places it in the `70_Drafts/[color]/Ready` folder.
 3. __Reviewer__ turns on track changes, creates MS Word comments. 
 4. If specified, __Reviewer__ completes an evaluation/compliance scorecard spreadsheet.
 5. When done with review, __Reviewer__ places document and scorecard in the `70_Drafts/[color]/Reviewed`
 6. When all reviews are done for a section, the __Proposal Manager__ consolidates reviews into a single document in the `Reviewed` folder. In this case, the PM puts the inidividual source review files in a `Reviewed/Original` subfolder.
 7. __Author__ takes the conslidated review document to move forward with edits.

## Folder Structure

Proposal folders are organized as follows ("#=>" is a comment):

```bash
Proposals/
  [Opportunity Name]/          #=> (see note below)
    00_Background/             #=> (SHARE) assorted research documents
    10_Teaming/
      NDAs/
      TAs/
    15_Shared_Team_Library/    #=> (SHARE) General docs to be shared across all team members
    [Specific Procurement]/    #=> example names: "RFP_2015_10_15", "RFI_2015_05_05"
      20_From_Government/      #=> (SHARE) procurement docs issued by government
      30_Question_to_Gov       #=> draft and submitted Pluribus questions regarding RFP
      50_Pricing/              #=> pricing source files
        Team_Input/
          SubA/                #=> can be shared w/ subs individually for input, data calls, collaboration
          SubB/
          ...
      70_Drafts/              #=> (SHARE) 
        Pink/
          Pink_Ready/         #=> drafts go here when ready for review
          Pink_Reviewed/      #=> reviewers place commented docs here
        Red/
        Gold/
      75_Graphics/            #=> (SHARE)
        Ready/                #=> drafts from authors
          Archive/
        Converted/            #=> "pretty" graphics from graphics SME
      90_Final_Submission_[DATE]/
        Source_Files/         #=> source text (ms word, excel, etc.) and graphics (ppt, vsd, psd, etc.)
        As_Submitted/         #=> exact files submitted to government
      9*_[Followup Submission Name]_[Date]/
```

Notes:

  * [DATE] is in YYYY_MM_DD format (e.g. "2013_12_25")
  * Organization under Proposals/[Opportunity Name] can be multiple levels. Target customers would have a dedicated folder, and probably subfolders for major initiatives (FDIC/ITAS-II, FDIC/Outsourcing). Others would be simply by agency or agency group (Defense).
  * The `9*_[Followup Submission Name]_[Date]/` folders are for things like BAFO, questions from government, etc. (e.g. "91_Questions_from_Agency_2015_10_21" or "92_BAFO_2015_10_30")
  * (SHARE) means that this would be shared with the broader proposal team (i.e. subcontractors)
