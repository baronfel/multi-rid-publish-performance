# Shared Roslyn Compilation with specialization for multiple projects

This repo is a sample of what you have to do to share a Roslyn Compilation between multiple RID and RID-less builds of the same project.
This prevents rebuilds of the same project for different RIDs, saving quite some time for larger repositories.

To see the changes, you can build the `PublishThreeTimes` project with the following commands:

```bash
dotnet build -c Release /t:PublishThreeTimes -bl
```

When this finishes, you can open the generated binlog and verify that only one Csc task was executed across the build.
