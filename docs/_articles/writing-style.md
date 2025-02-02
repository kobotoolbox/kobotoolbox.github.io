---
title: UI text writing style
TODO_NOTE: This article will need to be updated a bit when we switch to string identifiers in the UI code.
---

The rules are:

- Capitalize first letter of everything - from single words to sentences.
- Finish with a period only if it's a full sentence - e.g. not if it's a heading, short instruction, etc.
- Always make punctuation part of the translated string (so that RTL languages don't start with a period, for example).
- Use real ellipsis character (<code>…</code>) rather than three periods (<code>...</code>)<sup>1</sup>.
- Remember that our name is capitalized like this: `KoboToolbox` (and similarly `Kobo`).
- For translated text with placeholders, please use a descriptive text and wrap it in double hashes. E.g. for `Do you live in ##country name## right now?` the placeholder is `##country name##`.
- For translated text with links, please use a normal text and wrap it in square brackets. E.g. for `Plase [read the article] first!`, the whole text `read the article` would become a clickable link - the url will be provided by JS code. Example usage:
  <!-- {% raw %} -->
  ```ts
  // using utility function
  <span 
    dangerouslySetInnerHTML={{
      __html: replaceBracketsWithLink(t('Learn more [here].'), '<your URL>'),
    }} 
  />

  // using markdown
  const message = t('Please [contact us](##CONTACT_LINK##) to speak with our team.').replace('##CONTACT_LINK##', '<your URL>');
  ```
  <!-- {% endraw %} -->
- Use American English for UI text. The Merriam Webster dictionary is the first choice of dictionaries, and Oxford American is the second choice.

If in doubt, please mimic what is already there.

<small><sup>1</sup> On MacOS use `option` + `;`. On Windows it's `alt` + `0` `1` `3` `3` on the numberpad. Microsoft Office applications use `ctrl` + `alt` + `.`. On Linux, press `<compose key>` + `.` followed by `.`, or, if you do not have a compose key configured, press `ctrl` + `shift` + `u`, release, type `2`, `0`, `2`, `6`, and then press `enter`.</small>
