*This project has been created as part of the 42 curriculum by ebansse.*

# C++ Module 05: Repetition and Exceptions

Exercises on **exception handling** in C++98, built around a bureaucracy where bureaucrats with grades from 1 (highest) to 150 (lowest) sign and execute forms.

| Exercise | Program | Topic |
|---|---|---|
| `ex00` | `Bureaucrat` | A `Bureaucrat` class with a name and a grade. Raising or lowering the grade out of the 1 to 150 range throws `GradeTooHighException` / `GradeTooLowException` |
| `ex01` | `Form` | A `Form` with a required grade to sign and to execute. `Bureaucrat::signForm()` reports success, or explains why signing failed |
| `ex02` | `AForm` | `AForm` becomes an abstract class with three concrete forms (below). `Bureaucrat::executeForm()` executes a form only if it is signed and the grade is high enough |
| `ex03` | `Intern` | An `Intern` whose `makeForm(name, target)` looks the name up in a table of known forms and creates the matching one (or reports that the form doesn't exist) |

### The forms in ex02 and ex03

| Form | Sign grade | Exec grade | Action |
|---|---|---|---|
| `ShrubberyCreationForm` | 145 | 137 | writes ASCII trees to `<target>_shrubbery` |
| `RobotomyRequestForm` | 72 | 45 | makes drilling noises, then robotomizes the target with a 50% success rate |
| `PresidentialPardonForm` | 25 | 5 | announces that the target was pardoned by Zaphod Beeblebrox |

## Build & run

Each exercise has its own Makefile (`c++ -Wall -Wextra -Werror -std=c++98`):

```bash
cd ex03
make
./Intern
```

## Concepts covered

- Custom exception classes deriving from `std::exception` and overriding `what()`
- `try` / `catch` blocks and propagating exceptions to the caller
- Abstract classes and pure virtual functions
- Orthodox Canonical Form (default constructor, copy constructor, copy assignment, destructor)
- A simple factory that returns a base-class pointer (`Intern`)
