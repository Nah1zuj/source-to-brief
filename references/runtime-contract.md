# Runtime Contract

Use this contract internally before drafting. It is not a visible section in the final note unless the user asks for an audit.

## DocumentProfile

Build a compact profile:

- title
- author or creator, if available
- discipline
- material_type
- narrative_structure
- complexity: concise | standard | deep
- source_format
- language
- language_confirmed: yes | no
- reading_path
- local_profile, if user or workspace instructions define one

`narrative_structure` should describe how the final note will be organized, such as research-article, empirical-study, technical-paper, review-survey, theoretical-essay, textbook-chapter, lecture-handout, primary-text, case-study, policy-report, or multi-source-synthesis.

## ContentMap

Identify the reusable knowledge structure:

- core_question
- sub_questions
- key_concepts
- conceptual_relations
- argument_structure
- method_or_mechanism, when relevant
- evidence_or_textual_basis
- examples_or_cases
- objections_and_replies
- conclusions
- limitations

## ScholarshipMap

Use this map when scholarly expansion is appropriate:

- external_scholarship_status: not-needed | ask-user | user-approved | user-declined
- background_positioning
- explanatory_sources
- competing_views
- representative_debates
- critical_assessments
- bibliographic_verification
- references

External scholarship should support source reconstruction. It should not replace the source as the main object of the note.

## StudyOutputPlan

Before writing, choose:

- output_format: markdown | obsidian
- depth: concise | standard | deep
- language
- language_confirmed
- material_type_structure
- heading_style
- citation_style
- visual_elements: none | tables | mermaid | both
- destination_or_filename for the `.md` file
- batch_plan, if the material is too long for one pass

## Runtime Boundary

This contract guides reasoning and quality control. Do not print these maps as a checklist. Transform them into a clean note whose sections fit the discipline and material type.
