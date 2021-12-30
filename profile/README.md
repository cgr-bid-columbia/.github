# CGR-BID-Columbia Academic Team

**Principal Investigators:** [Michael Best](https://econ.columbia.edu/econpeople/michael-best/) (Columbia University), [Jonas Hjort](https://sites.google.com/site/jonashjort/) (University College London) and [Gaston Pierri](https://gastonpierri.com/) (IADB).

---
Welcome to our organization! We are an academic team composed of IADB, Columbia University and CGR Peruvian RAs supporting these PIs on _two main projects_:

- [The development of a set of Machine Learning Complaints algorithms](https://github.com/cgr-bid-columbia/users-guide/blob/main/complaints_guide.md)
- [A RCT to evaluate the quality of the "Monitores Ciudadanos" program](https://github.com/cgr-bid-columbia/users-guide/blob/main/mmcc_guide.md)

By clicking on a project name, you will access the user guide for the repositories related to each of them

### Structure of the Academic Team (Consultants only)

Our organigram can be found [here](https://docs.google.com/presentation/d/14rwj_Vp3KWuxNM8lidnvk24lUC07rtO1FIMUqsqzXUo/edit?usp=sharing). However, this can only be seen by organization members.

### Drive Folders (Consultants only)

- RAs drive folder [here](https://drive.google.com/drive/folders/1dsrhuF6yZLcRMOxV778vEiZXxlMbLF0b?usp=sharing)
- General drive folder [here](https://drive.google.com/drive/folders/1nRKfJIGGLXpHUM60K5ed3eJNvuUPsA9m?usp=sharing)

**Note:** While this README may be public, the guides regarding each project repos (as well as those repos) can only be seen by organization members.

---
## General Rules for Internal Tasks

### Softcoding

The general philosophy for our scripts should be to softcode them as much as possible. This implies that _paths variable values, server addresses and else_ must not be included directly onto our codes. To make this possible we can:

- Use system variables for `non-stata` scripts
- Ask the path directly to a `.do file` (stata script) user
- Create subdirectories directly from our scripts when neccesary

Regarding the _paths_, our scripts should not have a hardcoded path. Instead, we should use the following snippet to ask the current user the path where he/she will store the output of the respective script

```stata
di `"Please, input the path for storing the outputs of this dofile into the COMMAND WINDOW and then press ENTER  "'  _request(path)
cd "$path"
```

Regarding the subdirectories, one way to do that in stata is with this snippet:

```stata
global new_subdir_1 "$path/new_subdir_1"
cap mkdir "$new_subdir_1"
```

### Documentation

Our scripts must be documented. This means that they should be as self explanatory as possible. An optimal documentation can be achieved by:

- Adding short comments before a codeblock and _complicated_ lines of code
- Avoiding long statements. As a rule of thumb, a codeline should be shorter than the screen width (unless you use an ultrawide screen)
- Using variable, function, classes and object names that reflect what they represent
