# Whobbes.com/blog

A simple hugo blog

## Steps to add new content

1. `cd blog`

2. `hugo new posts/[title].md`

3. Edit md file header

4. Add image `{{< figure src="/images/[filename].jpg"  class="sml" width="50">}}`

5. Add score `<kbd>[number]%</kbd>`

6. Add break `<!--more--> / ***`

7. Test `hugo server -D`

8. Put draft to `false` and generate `hugo`

9. replace http to https in blog/index.html

10. Push to blog and newly created static content to whobbes.github.io

11. Job done, time for pasta Morty.
