# Java Style Guide
This project contains all style guides used for Java language files.

## Code Style
Our code style is based on [Google code style](https://google.github.io/styleguide/javaguide.html) with a few customizations.
The exact customizations and the reason behind each one of them is described below.
To check code style on source codes we use [Checkstyle](https://checkstyle.sourceforge.io/). Currently, version 8.45.1 of 
Checkstyle is recommended.

Fortunately, Checkstyle has defined most of the rules needed to check Google code style in a file in
their [repo](https://github.com/checkstyle/checkstyle).
This [file](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml) is our reference file
to check Google code style on our codes with some customizations.

### Customizations applied on reference file:
1. **Severity is changed to 'error' instead of 'warning':** Code style issues on our code base is treated as blocker issue
and no code with checkstyle issues is allowed to be merged.
2. **The column width is changed from 100 to 120:** Most of the monitors in our organization are enough wide to 
show 120 characters in a line without wrapping. Also, working with longer lines is easier and developers need
to wrap their lines less often.
3. **The indentation properties are all doubled:** We use 4 spaces to indent codes!
4. **MissingJavadocMethod rule is disabled:** This rule forces all developers to write javadoc for all public methods.
As stated in Google code style, writing javadoc for self-explanatory or obvious methods is not needed.
5. **SummaryJavadoc rule is disabled:** Sometimes we want to
only explain an input argument of a method or we want to just explain the thrown exceptions. Forcing developers
to write summary for all of javadocs will move their focus from important points to writing a summary to pass the checkstyle. 
6. **AvoidUnusedImports ruls is added:** Although this is not part of the Google Checkstyle, it has been added because it cleans the header of Java files by removing misleading references.