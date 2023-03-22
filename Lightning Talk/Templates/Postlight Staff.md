<%*

const name = await tp.system.prompt('Staff Name?');
if (!name) return;

const parts = name.split(' ');
const first = parts[0];
const last = parts[1];
const initials = `${first.charAt(0)}${last.charAt(0)}`;

const bobId = await tp.system.prompt('Bob ID');
if (!bobId) return;
const email = await tp.system.prompt('Email?');
const title = await tp.system.prompt('Title?');
const location = await tp.system.prompt('Location?');
const startdate = await tp.system.prompt('Start Date?');
const bday = await tp.system.prompt('Birthday (MM/DD)?');
const pronouns = await tp.system.prompt('Pronouns?');
const tags = await tp.system.prompt('Any tags?');

const fileName = `Postlight/Staff/${name}`;
const checkinDir = `Postlight/Staff/checkins/${first.toLowerCase()}_${last.toLowerCase()}`;

const fileContents = `---\naliases: [${first}, ${first.toLowerCase()}, ${initials}]\nemail: ${email}\nbob: https://app.hibob.com/employee-profile/${bobId}\ntitle: ${title}\nlocation: ${location}\nstartdate: ${startdate}\nbirthday: ${bday}\npronouns: ${pronouns}\ntags: ${tags}\n---

## notes
## project tasks
\`\`\`tasks
not done
description includes #postlight
\`\`\`
## topics to discuss
\`\`\`dataviewjs

dv.taskList(
  dv.pages()
    .file.tasks
    .where(
      t => !t.completed &&
      t.text.includes("@${first.toLowerCase()}")
    )
  );

\`\`\`
## projects
### current
* 

### past
- n/a

## checkins
\`\`\`dataview
LIST from "Postlight/Staff/checkins/${first.toLowerCase()}_${last.toLowerCase()}"
SORT file.name DESC
\`\`\`


`;

this.app.vault.createFolder(`${checkinDir}`);

tp.file.create_new(
  fileContents,
  fileName,
  true,
);

%>