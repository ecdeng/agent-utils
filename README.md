Repo for tracking the different utils that I've found useful for different projects with CLI agents (Claude Code and Gemini CLI). 

### X Bookmark --> Notion Reading List Subagent
Using the new [Claude in Chrome Extension](https://chromewebstore.google.com/detail/claude/fcoeoabgfenejglbffodgkkbkcdhcgfn) and the Notion MCP I built a simple subagent that goes through my X bookmarks and adds them into a reading list database in Notion. The agent will go through the bookmarks, select the subset that are "Reading List relevant", add them to the Notion, and unbookmark in X *when* it determines that the bookmark was added to the reading list database. This is a reasonably robust solution that can help you get around auth issues with X APIs as Claude is directly actuating on your logged in page. 

This is currently VERY SLOW but I don't really mind as it can run in the background. 

I've verified that all components work reasonably well with a small set of bookmarks: 
<img width="1512" height="506" alt="Screenshot 2025-12-30 at 6 53 42 PM" src="https://github.com/user-attachments/assets/e0393b12-ada4-4942-a74e-cb3453cde40d" />

Claude was able to determine which bookmarks were appropriate for a reading list and did not unbookmark the ones that it failed to add to Notion due to some issues w/ the MCP. 

<img width="1442" height="489" alt="Screenshot 2025-12-30 at 6 54 13 PM" src="https://github.com/user-attachments/assets/15c36826-176b-4fef-80ca-c6ca53ff0b4d" />

Confirmed that the Notion DB was updated with the correct information!

### Subagent Setup (Global setup recommended, easier to keep in sync across projects)
```
mkdir -p ~/.claude/agents
cp agents/*.md ~/.claude/agents/
```
