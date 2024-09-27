# Conference badge creator 

## Template Instructions
### What you need to do:
- Place your data in `participants.csv`. This might be exported from a spreadsheet program.
  The first line should contain the field headers -- avoid space characters in them.
- Commit

### What the code does for you:
- Loads the data file with `\DTLloaddb{data}{participants.csv}`.
  Replace with `\DTLloadrawdb{data}{participants.csv}` if you expect entries to contain special characters like `$`, `&`.
- Designs the badge using the `datatools` latex package.
- Uses the mapped commands to insert/change fields.
  ```
  \DTLforeach{data}{% for each row of data:
    \Name=Name,   % Map each column header to a command
    \Email=Email, ...}{ % Use them to insert field values e.g.
    Delegate name: \Name <\Email>  
  }
  ```
- Compile a pdf with all badges in github-actions
- Jam multiple badges in one page, adding cut-out margins
- Upload the jammed badges as artifact

