# Requirement analyze


## 1. Read requirment from Microsoft Word document and PDF file
* Convert data from Microsoft Word document and PDF file into text format for analysis.

### Use [markitdown](https://github.com/microsoft/markitdown)
```
$pip install markitdown
```

Run
```
$markitdown <input_file> -o <output_file>
```

## 2. Analyze the requirement
* Break down the requirement into functional and non-functional requirements.
* Identify any ambiguities or unclear points in the requirement.
* Prioritize the tasks based on dependencies and importance.
* Create a structured list of tasks categorized into functional and non-functional requirements, along with any relevant notes or clarifications.

### Use Agent ``Requirement analyze`` to analyze the requirement and generate a structured list of tasks