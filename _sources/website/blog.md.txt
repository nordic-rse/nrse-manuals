# Writing Blogs for Nordic-RSE

Everyone is encouraged to write a blog post for Nordic-RSE. Below you can find a few guidelines: 

## Topics

Anything that may be of interest to the Nordic-RSE community. Here are some ideas on what we have written blog posts before: 

- A new development wrt research software in the Nordics or one of the Nordic countries
- An event report
- A report about a related activity
- Organizers of conference discussions write about the discussion outcomes 

In addition these kind of topics could be of interest: 
- A specific tool or process that has helped you in your RSE work
- The structure and struggles of your RSE group
- Landscape overview, e.g. RSE training and the like
- Something you learned in a course, field report
- and many more...

## Authorship

Anyone who is involved in writing a blogpost can be a named author. 

- Multiple authors go comma-separated in the `author` field
- Posts written on behalf of a group can use the group as author, e.g. `"Nordic-RSE"` or `"Nordic-RSE 2025 organizing team"`.
- If AI tools helped write the post, mention it. 

### Use of AI

No fully AI-generated posts. AI tools can help with drafting or summarizing, but a human needs to stay in the loop: read, fact-check, and rewrite in your own voice before publishing. Making a post genuinely engaging — the personal angle, the specific details, the humor, what actually mattered to you about the event or topic — is something AI can't do for you; that part is on the human author.

## Length

The ideal blog lengts is something between 500 - 1000 words though depending on topic it can both be shorter or longer. Past posts range from about 100 words for a short announcement to about 3000 words for a survey analysis.

## Images

Images can make blogposts more interesting and engaging. You can add images like this: 

```
<img src="/blog/img/RSE-FI2026.jpg" style="width: 400px;" alt="Image collage of impressions from the Finnish RSE meetup 2026. Images show the group picture, a picture of a welcome sign, a presenter in front of their slides"/>
```

- Put the image file in `content/blog/img/` in the [website repository](https://github.com/nordic-rse/nordic-rse.github.io/tree/main/content/blog/img); it is then served at `/blog/img/<filename>`. If a post has many images, put them in a subfolder named after the post, e.g. `img/2026-07-30-rse-survey-analysis/`.
- Always add an `alt` text that describes what the image shows, for readers using screen readers.
- Set a size with `style`: `width: 400px;` works for photos and collages, `width: 100%;` for wide figures such as charts.

## Timeline, what to expect

We are a group of volunteers, please do not expect quick turnaround. It helps to use the chat to ask for review. Any board memeber or active member can approve PRs. 

## Style guide

Minimal header on top of each blog post file: 

```
+++
title = "This is the title of the blogpost"

[extra]

author = "One or multiple names of authors here"
+++
```

- Name the file `content/blog/YYYY-MM-DD-slug.md`, e.g. `2026-03-16-rse-fi.md`. The publication date is taken from the file name, so there is no `date` field.
- The title, author and date are shown automatically at the top of the post. Don't repeat the title as a `#` heading in the text.
- Use `##` for section headings. Many posts don't need any; past posts mix heading levels, so this is a convention for new posts.
- Link to sources, event pages and related posts inline, using normal Markdown links.

## Resources and Tips

Useful resources for writing blogposts: 

- [Institute for Research Software](https://www.software.ac.uk/guide/writing-institute-research-software-website)
- Scientific Collaboration and Community Engagement. (2020) Contributing to the CSCCE blog. Woodley, Garbee, and Pratt doi: 10.5281/zenodo.3924157


