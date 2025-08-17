# Your Unofficial Guide to Reviewing Papers

This guide is an unofficial guide for academic paper reviewing, professional conduct, and academic writing quality at TU Delft.

## 📋 Table of Contents

1. [Professional Conduct](#professional-conduct)
   - [Document Quality Standards](#document-quality-standards)
   - [Collaboration and Feedback](#collaboration-and-feedback)

2. [Paper Structure](#paper-structure)
   - [Standard Academic Paper Structure](#standard-academic-paper-structure)
   - [Detailed Paper Structure Guidelines](#detailed-paper-structure-guidelines)
     - [Title](#title)
     - [Abstract](#abstract)
     - [Introduction](#introduction)
     - [Related Work](#related-work-or-before-conclusions)
     - [Approach & Solution](#high-level-overview-of-approach--solution)
     - [Your Novel Theory / Experimental Setup / Architecture](#your-novel-theory--experimental-setup--architecture--)
     - [Experimental Results](#experimental-results)
     - [Conclusions](#conclusions)

3. [Document Reviewing](#document-reviewing)
   - [Three-Level Review Process](#three-level-review-process)
   - [Review Checklist](#review-checklist)
   - [Review Writing Guidelines](#review-writing-guidelines)

4. [Understanding Professor Feedback](#understanding-professor-feedback)
   - [Common Symbols and Abbreviations](#common-symbols-and-abbreviations)

## Professional Conduct

### Document Quality Standards

**Spelling and Grammar:**
- Always spell-check your documents before distribution
- Use tools like `ispell`, `detex`, `spell`, `latex2html`, WinEdit, or Word
- Asking readers to fix trivial errors is discourteous

**Document Structure:**
- **Page Numbers**: Always include page numbers in documents and presentations
- **Table of Contents**: Essential for documents longer than a few pages
- **Additional Lists**: For large documents (theses), include:
  - List of figures
  - Terminology
  - Abbreviations
  - Symbols
  - Definitions
  - Theorems
  - Index (very helpful for long documents)

### Collaboration and Feedback

**Paper Submission Process:**
1. Give co-authors sufficient time to review papers
2. Update git repository with submitted PDF in snapshot directory
3. Repeat process for final accepted version

**Plagiarism Prevention:**
- Clearly indicate when reusing text, figures, or data from other documents
- Avoid reusing text from your own papers in new papers (except extended journal versions)
- Self-plagiarism is not acceptable and leads to paper rejection

## Paper Structure

### Standard Academic Paper Structure

```
1. Title
2. Abstract
3. Introduction
4. Related Work
5. Problem Definition
6. Solution/Approach
7. Experiments/Evaluation
8. Results
9. Discussion
10. Conclusions
11. References
```

**Key Requirements:**
- Follow this structure for acceptance
- Reviewers expect this organization
- Deviations may lead to rejection

### Detailed Paper Structure Guidelines

#### Title
- *Nano version* of the paper: What is it about?

#### Abstract
- *Micro version* of the paper, focusing on:
  - Problem
  - Novelty
  - Claims
  - Possibly some high-level results
- Content:
  - Trends (leading to the problem)
  - Problem statement
  - Novelty & claims (in terms of approach, solution, results)
  - [Optional] High-level results

#### Introduction
- *Mini version* of the paper, focusing on:
  - Problem
  - Novelty
  - Claims
  - High-level approach & solution
- Content:
  - Trends (leading to the problem)
  - Problem statement
  - Novelty & claims
  - Approach & solution
  - Structure of paper
- **Note**: 
  - Repetition and recursion are useful
  - Explain the structure of your paper to the reader  
    (e.g., at the end of the introduction, and by linking sections)

#### Related Work (or before Conclusions)
- Explain how your work:
  - Differs from,
  - Improves on,
  - Extends,  
  other work  
- *Not just a list of other works!*

#### (High-level Overview of) Approach & Solution
- This section can be skipped, especially in shorter papers.

#### Your Novel Theory / Experimental Setup / Architecture / …
- Short introduction, linking to the previous section
- Subsections
- Short conclusion, linking to the next section

#### Experimental Results
- Explain the reason for the experiments  
  *(Hint: to prove your claims)*
- Then describe them
- **Explain** (not just describe) your experimental results
- Show that they prove your claims

#### Conclusions
- State that you solved the problem with your solution
- State that you proved your claims
- Include:
  - (Reminder of) Problem statement
  - (Reminder of) Solution (approach)
  - Results proving the claims

## Document Reviewing

### Three-Level Review Process

**Level 1: 3-5 Minutes (Fail-Fast)**
- Read only: title, abstract, conclusions, references
- Check: good English, clear problem, relevance, solution, citations
- Reject if any criteria not met
- Most people read papers this way

**Level 2: 10-15 Minutes (High-Level)**
- Also examine: figures, high-level approach, results section
- Check: solution understanding, experiment validity, claims proven
- Reject if criteria not met

**Level 3: 1+ Hour (Detailed)**
- Read everything, understand everything
- Almost no-one does this
- Reject only for real faults

### Review Checklist

**Content Verification:**
- Do title, abstract, introduction, and conclusions match?
- Are claims in abstract & introduction justified?
- Is problem defined well?
- Is solution and concepts defined well?
- Are limitations and constraints defined clearly?

**Structure and Presentation:**
- Is paper well-structured with proper sections, layout, figures?
- Is English understandable?
- Is there a related work section?
- Is related work correct and fair to other papers?

**Experiments and Results:**
- Are experiments defined in sufficient detail?
- Are experiments presented well (understandable graphs)?
- Are conclusions from experiments justified?
- What is the novelty of the paper?

### Review Writing Guidelines

**Professional Conduct:**
- Be polite and don't offend authors
- Write impersonal reviews: "the text is difficult to understand" not "I don't understand"
- Give suggestions for improvement
- Review to same standard regardless of venue

**Revision Responses:**
- Include cover letter thanking reviewers and editor
- Respond to each comment in detail
- Ensure each response results in visible changes

## Understanding Professor Feedback

### Common Symbols and Abbreviations

**Approval Indicators:**
- **C**: OK
- **~**: OK-ish
- **✓**: Good

**Problem Indicators:**
- **?**: Unclear (larger = bigger problem)
- **×, n**: Not OK (larger = bigger problem)
- **≠**: Inconsistent, incorrect

**Structural Changes:**
- **large ~ between words**: Swap these parts
- **\\**: Break into two paragraphs or lines
- **×**: Join two parts (paragraphs, sentences)

**Logical Connectives:**
- **⇒**: Implies
- **/⇒**: Non sequitur (does not follow)
- **∴**: Therefore
- **∵**: Because

**References:**
- **②, ①, ②**: Text referred to later/elsewhere

**Common Abbreviations:**
- **o/w**: Otherwise
- **w/o**: Without
- **w/**: With
- **p/pp**: Page/pages
- **def/(un)def'd**: Definition/(un)defined
- **emph/it**: Emphasize/italicize
- **ip/op**: Input/output
- **(dis)cts**: (Dis)continuous
- **reqˢ/respˢ**: Request(s)/response(s)
- **trans**: Transaction
- **beh**: Behaviour
- **eqn**: Equation