# Conference badge creator 

## Template Instructions
### What you need to do:
- Create a copy of this repo template, using <a href="https://github.com/new?template_name=template-project&template_owner=RiccardoBuscicchio"><img src="https://img.shields.io/badge/this-template-blue?logo=github"></a>
- Grant "Read and Write access" to Github Actions for the newly created repository (Settings-->Actions)
- Place your participants data in `participants.csv`.
  This might also be easily exported from any spreadsheet manager software.
  The first line should contain the field headers -- avoid space characters in them.
- Commit

### What the code does for you:
- Loads the data file with `\DTLloaddb{data}{participants.csv}`.
- (Replace with `\DTLloadrawdb{data}{participants.csv}` if you expect entries to contain special characters like `$`, `&`.)
- Designs the badge using the `datatools` latex package.
- Uses the mapped commands to insert/change fields.
  ```
  \DTLforeach{data}{% for each row of data:
    \Name=Name,   % Map each column header to a command
    \Email=Email, ...}{ % Use them to insert field values e.g.
    Delegate name: \Name <\Email>  
  }
  ```
- Creates a barcode for each participant
- Adds each barcode to each participant's badge
- Compiles a pdf with all badges in github-actions
- Jams multiple badges in one page, adding cut-out margins
- Uploads the jammed badges as artifacts to the orphan branch `build`


