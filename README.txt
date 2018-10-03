This describe the steps to create content for my Hugo Blog:

1. cd blog

2. hugo new posts/[title].md

3. edit md file header

4. Add image with following snippet -->
{{< figure src="/images/[filename].jpg"  class="sml" width="50">}}

4. Add score with <kbd>[number]%</kbd>

5. Add break with <!--more--> / ***

6. test with hugo server -D

7. Put draft to false and generate with command hugo

8. Now push the blog to save changes and push whobbes.github.io to add statically generated pages to main website.

9. Job done, time for pasta Morty.
