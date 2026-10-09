# TeensPro — Your Future, Your Path

**Building AI course project**

## Summary

TeensPro is an AI-powered education and career navigator for teenagers aged 14–17 in Belarus, Georgia, Armenia, Kyrgyzstan, and Tajikistan. It helps users explore careers, understand possible study paths, and discover education and funding opportunities that may fit their citizenship, age, academic stage, interests, and language skills.

## Background

Choosing a career and planning education can be difficult, especially when reliable information is scattered across university websites, scholarship portals, and resources published in different languages. Teenagers may not know which careers match their interests, what qualifications are needed, or which opportunities they can realistically prepare for.

TeensPro aims to make this information easier to understand and act on. Instead of giving users a long list of links, it connects three questions:

- **What might suit me?** Explore career areas based on interests, favourite subjects, activities, and personal goals.
- **What pathways are available?** Compare relevant study routes, such as local education, vocational training, undergraduate study, and later postgraduate opportunities.
- **What can I do next?** Get a practical checklist of requirements, documents, language preparation, and application dates.

The first target audience is teenagers aged 14–17 in Belarus, Georgia, Armenia, Kyrgyzstan, and Tajikistan, as well as their parents and school counsellors. The project is motivated by the idea that a lack of guidance or accessible information should not prevent young people from exploring their options.

TeensPro is designed as an information and planning aid, not as an admissions authority or a system that decides a teenager’s future.

## How is it used?

A typical user journey could look like this:

1. **Create a basic profile.** The user selects their country of citizenship, age range, school grade or current education stage, preferred languages, and areas of interest. The platform should collect only the information needed for recommendations.
2. **Explore interests and strengths.** The user answers a short questionnaire about favourite subjects, activities, skills they would like to develop, and preferred types of work. Results are presented as possibilities to explore, not as a definitive psychological assessment.
3. **Explore career directions.** TeensPro suggests several career areas and explains why each may be relevant. It also shows related subjects and possible education routes.
4. **Find education and funding options.** The platform searches a curated catalogue of study programmes, scholarships, and other funding opportunities. Results are filtered by relevant criteria such as citizenship, education level, destination, field of study, and application period.
5. **Check the original source.** Each opportunity includes a link to its official programme or university page, the date it was last checked, and a clear distinction between verified information and information that still needs confirmation.
6. **Build a roadmap.** The user can create a timeline of next steps—for example, improve a language level, research programmes, prepare documents, ask a teacher for a reference, and check the next application opening date.
7. **Review with an adult or counsellor.** Users can discuss the results with a parent, teacher, or qualified adviser before making important decisions.

### Example

A student interested in biology and environmental issues might receive several career areas to explore, such as environmental science, laboratory work, or sustainable agriculture. TeensPro would then show possible education routes and relevant opportunities, if any are listed in the verified catalogue. It would explain the requirements and link to official sources rather than promising that the student qualifies or will receive funding.

## Data sources and AI methods

The quality and freshness of the information are essential. The first version should use a small, curated dataset and expand only when sources and eligibility rules can be checked reliably.

### Planned data sources

- **Official scholarship and programme pages**, including the [Erasmus Mundus Joint Masters](https://erasmus-plus.ec.europa.eu/opportunities/individuals/students/erasmus-mundus-joint-masters) programme information, the [Chevening eligibility guidance](https://www.chevening.org/resource-hub/guidance/eligibility/), and the [DAAD scholarship database](https://www.daad.de/en/studying-in-germany/scholarships/daad-scholarships/).
- **Official university websites** for admission requirements, degree options, tuition fees, language requirements, and application dates.
- **Official national education and career resources**, where available, for local education pathways and qualification information.
- **A career-information catalogue** created from appropriately licensed or openly available descriptions of occupations, skills, and related subjects.
- **User-provided preferences**, such as interests, favourite subjects, education stage, and language skills. These should be optional where possible and handled with particular care because many users are minors.

Every opportunity record should include, where available: programme name, official URL, eligible citizenship or residency conditions, education level, field, destination, required qualifications, language requirements, funding coverage, opening and closing dates, last-checked date, and a note about uncertainty. Missing information should be labelled as unknown rather than guessed.

### Planned AI methods

- **Rule-based filtering:** First remove opportunities that clearly do not match essential criteria, such as education level or stated citizenship requirements. The rules must reflect each programme’s official terms and should not assume that all programmes use citizenship in the same way.
- **Recommendation system:** Rank the remaining career areas and opportunities according to the user’s stated interests, education stage, preferred subjects, and goals. Recommendations should be explainable, with a short reason for each result.
- **Natural language processing (NLP):** Help extract structured fields—such as deadlines, required documents, and language levels—from programme pages for human review. Extracted details should not be published as verified until checked against the source.
- **Large language model (LLM):** Explain requirements in simpler language, answer questions using the curated information, and help turn verified requirements into a checklist. The assistant should cite the source for factual answers and say when it cannot confirm something.
- **Human review and feedback:** A maintainer or education adviser checks high-impact details and user feedback is used to improve clarity and relevance.

For a first prototype, the project does not need a complex machine-learning model. A transparent catalogue, eligibility filters, and a simple ranking method would be enough to demonstrate the concept. More advanced AI could be added after the data and evaluation process are reliable.

### Example data structure

```python
opportunity = {
    "name": "Example scholarship",
    "official_url": "https://example.org/programme",
    "eligible_citizenships": [],
    "education_level": "undergraduate",
    "fields": [],
    "language_requirements": [],
    "funding_details": "Check the official programme page",
    "application_deadline": None,
    "last_checked": None,
    "verification_status": "needs_review"
}
```

This is an illustrative structure, not a real scholarship listing. The prototype should never display invented deadlines, funding amounts, or eligibility claims as facts.

## Challenges

TeensPro cannot solve every problem related to education access. Important limitations and risks include:

- **Changing requirements:** Scholarship eligibility, deadlines, funding, and admission rules may change. A listing can become outdated, so the service needs source links, last-checked dates, and a way to report errors.
- **Incomplete information:** Some programmes do not publish every detail in one place, and not every opportunity has a reliable machine-readable source.
- **Eligibility is programme-specific:** Citizenship, residency, age, degree level, work experience, language proficiency, and other conditions vary. A broad country filter alone is not enough to determine eligibility.
- **Recommendation bias:** A system may over-recommend familiar or well-documented careers and overlook less common paths. Users should be shown a range of options and be able to change their preferences.
- **Over-reliance on AI:** A career suggestion is not a diagnosis or a final decision. Shturman should explain uncertainty and encourage users to discuss important choices with trusted adults or qualified advisers.
- **Privacy and child safety:** Many users are minors. The service should minimise data collection, use clear consent and privacy practices, protect stored data, and avoid collecting sensitive details that are not necessary for the service.
- **Accessibility and language:** Users may have different levels of English and different access to devices or reliable internet. Clear language and, where feasible, local-language support are important.
- **No guarantee of outcomes:** Shturman cannot guarantee admission, a visa, a scholarship, or employment. Official institutions make those decisions.

The project should be evaluated for factual accuracy, usefulness, fairness across the five target countries, and whether users understand that recommendations are guidance rather than guarantees.

## What next?

The project could grow in stages:

1. **Build a small prototype:** Create a curated dataset of a limited number of career areas and verified education opportunities, with official links and review dates.
2. **Test the user journey:** Ask teenagers, parents, and school counsellors to review sample recommendations and identify confusing or missing information. Participation by minors should follow appropriate consent and safeguarding practices.
3. **Measure quality:** Track whether links are current, whether extracted requirements match official sources, how often recommendations are relevant, and whether users understand the limitations.
4. **Add language support:** Provide plain-language explanations and gradually support the languages most useful to the target communities.
5. **Create a maintenance process:** Set a schedule for reviewing sources and a clear process for users to flag outdated or incorrect listings.
6. **Work with partners:** Seek feedback from schools, education advisers, youth organisations, universities, and scholarship providers.
7. **Expand carefully:** Add more programmes and countries only when eligibility information can be maintained reliably.
8. **Develop a full service:** If the prototype proves useful, consider a mobile-friendly website, personalised reminders, and a counsellor view—while maintaining strong privacy protections.

Skills and support that would help include basic web development, data cleaning, NLP, recommendation systems, user research, accessibility, and advice from education professionals.

## Acknowledgments

- **Elements of AI / Building AI**, created by Reaktor Innovations and the University of Helsinki, for the course framework and final-project guidance.
- **Erasmus+ / Erasmus Mundus**, for official programme information: https://erasmus-plus.ec.europa.eu/opportunities/individuals/students/erasmus-mundus-joint-masters
- **Chevening**, for official eligibility guidance: https://www.chevening.org/resource-hub/guidance/eligibility/
- **DAAD**, for official scholarship information: https://www.daad.de/en/studying-in-germany/scholarships/daad-scholarships/

This project description is a proposal. Programme names and links are starting points for research, not confirmation that a particular opportunity is currently open or available to every student in the five target countries. All eligibility details, funding amounts, and deadlines must be checked against the official programme pages before being shown to users.
