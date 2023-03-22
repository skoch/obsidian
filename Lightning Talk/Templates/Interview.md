<%*

const name = await tp.system.prompt('Who are you interviewing today?');
if (!name) {
  return;
}

const fileName = `Postlight/Interviews/${name}`;
const fileContents = tp.file.find_tfile('Interview Questions');

tp.file.create_new(
  fileContents,
  fileName,
  true,
);

%>
