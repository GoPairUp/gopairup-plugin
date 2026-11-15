# GoPairUp

[GoPairUp](https://gopairup.com) helps elementary teachers pair up students, run centers and
play quiz games on the classroom whiteboard. This plugin connects Claude to your GoPairUp
account, so you can manage your classes and write quizzes by asking in your own words.

## What's in it

- **The GoPairUp connector** (`https://gopairup.com/mcp`). It lets Claude read your classes,
  make and shuffle groups, move students, mark absences, keep pairs of students apart, manage
  rosters, and find, save and change quizzes. [Use with Claude or ChatGPT](https://gopairup.com/connect)
  lists every tool.
- **Group the class**, a skill for making today's groups: who is out, how many groups, who
  works apart, and a short summary you can read to the class.
- **Write a quiz**, a skill for writing a quiz game at your class's grade, tied to state
  standards, with an optional exit ticket, and saving it to GoPairUp for you to review.

## Set up

1. Add the plugin, then open its **Connectors** tab and connect GoPairUp.
2. Sign in to GoPairUp when it asks (or create a free account), and press **Allow**.
3. Ask Claude something like:
   - "Make groups of four for Period 2. Maya and Leo are out today."
   - "Keep Sam and Ava apart in my morning class from now on."
   - "Write a 10-question quiz on the water cycle for my 3rd graders and save it."
   - "Find my fractions quiz and add three harder questions."

Grouping and rosters are free. Saving quizzes from Claude needs the GoPairUp monthly plan.

## Data

The plugin runs nothing on your computer. Claude talks only to GoPairUp, at
`https://gopairup.com/mcp`, over your own signed-in connection. It reads and changes your
classes and quizzes there, students' names included, since it needs them to make groups.
What Claude reads goes to Anthropic under your Claude account and its settings. Quizzes never
include students' names. GoPairUp never sees your email or password through the connection,
and you can revoke it at any time in GoPairUp's Settings, under Connected apps.

See [Privacy and your data](https://gopairup.com/privacy),
[Student data privacy](https://gopairup.com/schools) and the
[Terms of Service](https://gopairup.com/terms).

## Support

Email [support@gopairup.com](mailto:support@gopairup.com), or see
[Help](https://gopairup.com/help).

## License

MIT, © Eclarius LLC. See [LICENSE](LICENSE).
