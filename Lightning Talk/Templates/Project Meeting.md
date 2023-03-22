<%*
// Get a list of projects
const { folders } = await this.app.vault.adapter.list("/Postlight/Projects");
const projects = folders.map(f => f.split("/").pop());
const project = await tp.system.suggester(projects, projects);

if (!project) { 
  return;
}

const fileName = `${project} ${tp.date.now("Y-MM-DD")}`;
const filePath = `Postlight/Projects/${project}/meetings/${fileName}`;
const fileContents = `---\ntags: meeting\n---\n\nMeeting for [[${project}]] on ${tp.date.now("MMMM D, Y @ HH:mm")}

## notes
- 

`

await tp.file.create_new(
  fileContents,
  filePath,
  true,
);
%>
