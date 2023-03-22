<%*

// Get a staff listing
const { files } = await this.app.vault.adapter.list("/Postlight/Staff");
const reports = files.filter(f => !f.endsWith("Reports.md")).map(f => f.split("/").pop().slice(0, -3))

const name = await tp.system.suggester(reports, reports);
if (!name) {
  return;
}

const firstname = `${name.toLowerCase().split(' ')[0]}`;
const pathComponent = name.toLowerCase().replace(" ", "_");
const fileName = `Postlight/Staff/checkins/${pathComponent}/${name} ${tp.date.now("Y-MM-DD")}`;
const fileContents = `---\ntags: 1:1\n---\n\nCheckin with [[${name}]] on ${tp.date.now("MMMM D, Y @ HH:mm")}

## notes
- 

## tagged tasks
\`\`\`dataviewjs

// any incomplete tasks that are tagged '@${firstname}'
dv.taskList(
  dv.pages('-"Templates"')
    .file.tasks
    .where(
      t => !t.completed &&
      t.text.includes("@${firstname}")
  )
);

\`\`\`

`

tp.file.create_new(
  fileContents,
  fileName,
  true,
);

%>


