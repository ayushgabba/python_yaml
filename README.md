# Python YAML Use Case

## Introduction
This project demonstrates how to use YAML in Python to store and filter student data. The application reads student information from a YAML file, displays the data, and allows filtering based on GPA.

## Prerequisites
- Python installed on your system
- Install `PyYAML` package using:

```
 pip install pyyaml
```

## Files Included
1. `students.yaml` - YAML file containing student data.
2. `app.py` - Python script to read and filter students from the YAML file.

## Creating the YAML File
Create a file named `students.yaml` and add the following content:
```
students:
  - name: Alice
    age: 21
    major: Computer Science
    gpa: 3.8
  - name: Bob
    age: 22
    major: Mathematics
    gpa: 3.5
  - name: Charlie
    age: 20
    major: Physics
    gpa: 3.9
  - name: David
    age: 23
    major: Chemistry
    gpa: 3.2
  - name: Eva
    age: 21
    major: Computer Science
    gpa: 3.7
```

## Python Script
Create a file named `app.py` and add the following code:
```
import yaml

def load_data(file_path):
    """Load data from a YAML file."""
    with open(file_path, 'r') as file:
        data = yaml.safe_load(file)
    return data

def display_students(students):
    """Display all students."""
    print("\nAll Students:")
    for student in students:
        print(f"Name: {student['name']}, Age: {student['age']}, Major: {student['major']}, GPA: {student['gpa']}")

def filter_students_by_gpa(students, min_gpa):
    """Filter students by GPA."""
    filtered_students = [s for s in students if s['gpa'] >= min_gpa]
    print(f"\nStudents with GPA >= {min_gpa}:")
    if filtered_students:
        for student in filtered_students:
            print(f"Name: {student['name']}, Age: {student['age']}, Major: {student['major']}, GPA: {student['gpa']}")
    else:
        print("No students found.")

def main():
    data = load_data('students.yaml')
    students = data['students']
    display_students(students)
    min_gpa = float(input("\nEnter minimum GPA to filter students: "))
    filter_students_by_gpa(students, min_gpa)

if __name__ == "__main__":
    main()
```

## Running the Application
Ensure `students.yaml` and `app.py` are in the same directory. Run the script using:
```
python app.py
```

### Expected Output
```
All Students:
Name: Alice, Age: 21, Major: Computer Science, GPA: 3.8
Name: Bob, Age: 22, Major: Mathematics, GPA: 3.5
Name: Charlie, Age: 20, Major: Physics, GPA: 3.9
Name: David, Age: 23, Major: Chemistry, GPA: 3.2
Name: Eva, Age: 21, Major: Computer Science, GPA: 3.7

Enter minimum GPA to filter students: 3.6

Students with GPA >= 3.6:
Name: Alice, Age: 21, Major: Computer Science, GPA: 3.8
Name: Charlie, Age: 20, Major: Physics, GPA: 3.9
Name: Eva, Age: 21, Major: Computer Science, GPA: 3.7
```

## Uploading to GitHub
### Initializing Git Repository
```
git init
git add .
git commit -m "Initial commit - Added Python script and YAML file"
```
### Adding Remote Repository
Replace `<your-username>` with your GitHub username and `<your-repo-name>` with the name of your repository:
```
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git branch -M main
git push -u origin main
```

### Handling Errors
If you encounter an error:
```
git pull origin main --rebase
git push origin main
```
If necessary, force push:
```
git push origin main --force
```

## Conclusion
This project demonstrates how to use YAML in Python to store and filter student data. You can expand this application by adding functionalities such as sorting, updating, or saving changes back to the YAML file.

---

Enjoy coding! 🚀
