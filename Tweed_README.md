// index.js

const { Probot } = require('probot');

// Initialize a new Probot instance
const probot = new Probot({});

// Event listener for when the app is loaded
probot.load(app => {
  // Listen for issue or pull request comments
  app.on('issue_comment.created', async context => {
    const comment = context.payload.comment.body;
    const issueNumber = context.payload.issue.number;

    // Check if the comment is a command
    if (comment.startsWith('/hello')) {
      // Respond with a greeting
      const response = 'Hello there! :wave:';
      await context.octokit.issues.createComment(context.repo({ issue_number: issueNumber, body: response }));
    } else if (comment.startsWith('/help')) {
      // Respond with a help message
      const response = 'I can help you with various tasks. Try using /hello to greet me!';
      await context.octokit.issues.createComment(context.repo({ issue_number: issueNumber, body: response }));
    }
  });
});

// Start the Probot app
probot.start();

- 👋 Hi, I’m @Tweemovie
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Tweemovie/Tweemovie is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
