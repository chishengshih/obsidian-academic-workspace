# Obsidian Academic Workspace

## Required plugins

- Kanban.
- Tasks.

## Structure

- The attachments folder contains all attachments such as screenshots.
- The templates folder contains all the templates, which are listed and explained in the Templates section below.
- The courses folder contains course notes for courses that I attend.
- The info folder contains useful info such as a note with all the relevant info for my CV.
- The project folder contains notes and kanban boards for non-academic projects.
- The research folder contains notes and kanban boards for academic projects, and it also contains a folder with notes and kanban boards for research papers that I read.
- The trips folder contains notes to prepare and plan trips.
- The tasks are handled by a single global tasks file, as exlpained in the Task Workflow section below.

## Templates

This vault uses a small set of templates with short, consistent names.

**Naming rule:** the noun alone usually refers to the main note or hub; **Board** refers to a Kanban/progress-tracking note.

### Template types

- **Course** — hub and notes for a course I am taking or teaching.
- **Lecture** — notes for a single lecture, either one I attend or one I teach.
- **Paper** — notes, remarks, and ideas related to a research paper I have read or am reading.
- **Paper Board** — Kanban board for tracking the progress of reading research papers.
- **Project** — hub for a non-academic project.
- **Project Board** — Kanban board for tracking the progress of a project.
- **Research** — hub for an academic project.
- **Talk** — notes for a research, seminar, or similar talk, either one I attend or one I give.
- **Trip** — planning notes and information for a trip.

## Task Workflow

All tasks are stored in a single master note:

```text
Tasks.md
```

This file is the **single source of truth** for tasks in the vault. Tasks should be written as ordinary Markdown checkboxes, for example:

```markdown
- [ ] Buy groceries
- [ ] Book hotel +Japan-Trip
- [ ] Read chapter 3 +Algebraic-Geometry-Course
- [ ] Contact collaborator +Derived-Equivalence
```

The [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks) plugin is used only to **display filtered views** of these tasks elsewhere in the vault. Completing a task from one of these views updates the corresponding task in `Tasks.md`.

### Dashboard

The Dashboard displays all open tasks from `Tasks.md`:

````markdown
```tasks
not done
filename includes Tasks.md
hide backlinks
hide task count
hide toolbar
hide edit button
```
````

This provides a global overview without duplicating task data.

### Assigning Tasks to Notes

Tasks can be associated with a particular trip, project, research project, or course using a `todo.txt`-style `+Project` identifier.

The identifier corresponds to the filename of the relevant note, without the `.md` extension.

For example:

```text
Japan-Trip.md                → +Japan-Trip
Derived-Equivalence.md       → +Derived-Equivalence
Algebraic-Geometry-Course.md → +Algebraic-Geometry-Course
```

A corresponding task in `Tasks.md` might therefore look like:

```markdown
- [ ] Reserve accommodation +Japan-Trip
- [ ] Check the literature on c2 +Derived-Equivalence
- [ ] Prepare next lecture +Algebraic-Geometry-Course
```

For this reason, notes using this workflow should have filenames without spaces, using hyphens instead.

### To-do Sections in Notes

The relevant templates contain a `## To-do` section that automatically displays the open tasks associated with that note.

This applies to:

- project notes;
- course notes;
- trip notes.	

Each of these notes uses its own filename as its `+Project` identifier. For example, the `## To-do` section of `Japan-Trip.md` displays open tasks containing `+Japan-Trip`.

The task itself always remains in `Tasks.md`; the individual note only contains a filtered Tasks view.

### General Convention

The resulting workflow is:

```text
Tasks.md
    │
    ├── general task
    ├── task +Trip-Name
    ├── task +Project-Name
    └── task +Course-Name
             │
             ▼
Dashboard / Trip / Project / Course
             │
             └── filtered Tasks views
```

Use `Tasks.md` for editing and maintaining the master task list, and use the Dashboard and individual notes as contextual views of the same underlying tasks.

Tasks that do not belong to any particular note can simply be left without a `+Project` identifier.
