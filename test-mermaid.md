## Block-Beta 1 (neutral theme)

```mermaid
---
config:
  theme: neutral
---
block-beta
    columns 5
    CLI["⭐ CLI Input\nyoutube-to-xml\ntranscript.txt"] space MAIN["main.py\n(orchestrate)"] space VALIDATOR["validator.py\n(check format)"]
    space space space space space
    space space FILEREAD["file_handler.py\n(read file)"] space space
    space space space space space
    space space PARSER["parser.py\n(find chapters)"] space XMLGEN["xml_generator.py\n(build XML tree)"] space
    space space space space space
    space FILEWRITE["file_handler.py\n(write XML)"] space OUTPUT["🎯 Output\ntranscript_files/\noutput.xml"]
    CLI --> MAIN
    MAIN --> VALIDATOR
    MAIN --> FILEREAD
    VALIDATOR --> FILEREAD
    FILEREAD --> PARSER
    PARSER --> XMLGEN
    PARSER --> FILEWRITE
    XMLGEN --> OUTPUT
    style CLI fill:#8ec9ff,stroke:#46637e,stroke-dasharray: 5 5
    style OUTPUT fill:#90cc9b,stroke:#354c39,stroke-dasharray: 5 5
```

## Block-Beta 2 (neo-dark)

```mermaid
---
config:
  theme: neo-dark
---
block-beta
    columns 5
    CLI["User Command:\n`youtube-to-xml\nfile.txt`"] space FILEREADER["File Reader\n(file_io.py)"] space PARSER["Parser\n(parser.py)"]
    space space space space space
    XMLOUTPUT["XML Output\ntranscript_files/\nfile.xml"] space XMLBUILDER["XML Builder\n(xml_builder.py)"] space CHAPTERLIST["Chapter List\n[Chapter(...)]"]
    CLI --> FILEREADER
    FILEREADER --> PARSER
    PARSER --> CHAPTERLIST
    CHAPTERLIST --> XMLBUILDER
    XMLBUILDER --> XMLOUTPUT

    style CLI color:#fff,fill:#3874ac,stroke:#000,stroke-dasharray: 5 5
    style XMLOUTPUT color:#fff,fill:#419f52,stroke:#000,stroke-dasharray: 5 5
```

## Flow chart (redux-dark theme, dagre layout, markdown)

```mermaid
---
title: Git Branch Workflow
config:
  look: neo
  layout: dagre
  theme: redux-dark
  htmlLabels: false
---
flowchart TD
    START(["`**Start on main**
    git checkout main
    git pull origin main`"]) --> CREATE["`**Create branch**
    git checkout -b my-branch`"]
    CREATE --> WORK["`**Do commits**
    git add .
     git commit`"]
    WORK --> PUSH["`**Push to remote**
    git push origin my-branch`"]
    PUSH --> PR["`**Create Pull Request**
    GitHub: New PR, select
    my-branch -> main`"]
    PR --> REVIEW["`**Code review**
    GitHub: Review
    changes in PR`"]
    REVIEW --> APPROVE["`**Approve & merge PR**
    *GitHub Choices:*
    a)Merge commit →⭐visual
    b)Rebase merge →✅clean
    c)Squash merge →v.sparse`"]
    APPROVE --> SYNC["`**Sync local main**
    git checkout main
    git pull origin main`"]
    SYNC --> CLEANUP["`**Delete branch (2 steps)**
    git branch --delete my-branch
    git push origin --delete my-branch`"]
    CLEANUP --> NEXT["`**Ready for next branch**`"]
    NEXT -.-> |Create next branch| CREATE
```

---

## Try again 1

```mermaid
---
config:
  theme: redux
  markdownAutoWrap: false
---
flowchart TD
    CLI@{ shape: lean-r, label: "User Command\n\"youtube-to-xml transcript.txt\"" }
    CLIMOD["`**cli.py**
    • Parse args
    • File I/O operations
    • Error handling
    • Orchestration`"]
    EXCEPTIONS["`**exceptions.py**
    • EmptyFileError
    • InvalidTranscriptFormatError
    • MissingTimestampError`"]
    PARSER["`**parser.py**
    • Validate format
    • Find chapters
    • Extract content`"]
    XMLBUILDER["`**xml_builder.py**
    • Generate XML
    • Handle escaping`"]
    OUTPUT["`**transcript_files/**
    └── transcript.xml
    (output file)`"]
    CLI --> CLIMOD
    CLIMOD --> |Raw text<br>as string| PARSER
    PARSER --> |"List[Chapter]<br>(frozen dataclass)"| XMLBUILDER
    XMLBUILDER --> |XML string| CLIMOD
    CLIMOD --> OUTPUT
    EXCEPTIONS -.-> PARSER
    EXCEPTIONS -.-> CLIMOD

    style CLI color:#fff,fill:#3874ac,stroke:#000,stroke-dasharray: 5 5
    style OUTPUT color:#fff,fill:#419f52,stroke:#000,stroke-dasharray: 5 5
    style EXCEPTIONS color:#fff,fill:#e74c3c,stroke:#000,stroke-dasharray: 3 3
```

## Try again 2

```mermaid
---
config:
  theme: redux
---
flowchart TD
    subgraph TOP[" "]
        direction LR
        CLI["`**User Command**
        youtube-to-xml
        transcript.txt`"]
        CLIMOD["`**cli.py**
        • Parse args
        • File I/O operations
        • Error handling
        • Orchestration`"]
        OUTPUT["`**transcript_files/**
        └── transcript.xml
        (output file)`"]
        CLI --> CLIMOD
        CLIMOD --> OUTPUT
    end
    
    EXCEPTIONS["`**exceptions.py**
    • EmptyFileError
    InvalidTranscriptFormatError
    • MissingTimestampError`"]
    
    PARSER["`**parser.py**
    • Validate format
    • Find chapters
    • Extract content`"]
    
    XMLBUILDER["`**xml_builder.py**
    • Generate XML
    • Handle escaping`"]
    
    CLIMOD --> |Raw text<br>as string| PARSER
    PARSER --> |"List[Chapter]<br>(frozen dataclass)"| XMLBUILDER
    XMLBUILDER --> |XML string| CLIMOD
    EXCEPTIONS -.-> PARSER
    EXCEPTIONS -.-> CLIMOD
    
    style CLI color:#fff,fill:#3874ac,stroke:#000,stroke-dasharray: 5 5
    style OUTPUT color:#fff,fill:#419f52,stroke:#000,stroke-dasharray: 5 5
    style EXCEPTIONS color:#fff,fill:#e74c3c,stroke:#000,stroke-dasharray: 3 3
    style TOP fill:none,stroke:none
```

## Try 3

```mermaid
---
config:
  theme: neutral
---
block-beta
    columns 5
    CLI["CLI Input\nyoutube-to-xml\ntranscript.txt"] space CLIMOD["cli.py\n(orchestrate)\n(file I/O)"] space OUTPUT["transcript_files/\ntranscript.xml"]
    space space space space space
    space EXCEPTION["exceptions.py\n(parsing errors)"] space space space
    space space space space space
    space space PARSER["parser.py\n(validate format)\n(find chapters)"] space XMLBUILDER["xml_builder.py\n(generate XML)\n(handle escaping)"]

    CLI --> CLIMOD
    CLIMOD --> PARSER
    PARSER --> XMLBUILDER
    XMLBUILDER --> CLIMOD
    CLIMOD --> OUTPUT
    EXCEPTION --> CLIMOD
    EXCEPTION --> PARSER
```
