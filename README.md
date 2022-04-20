# Java Style Guide
This project contains all style guides used for Java language files.

## Code Style
Our code style is based on [Google code style](https://google.github.io/styleguide/javaguide.html) with a
few customizations. The exact customizations and the reason behind each one of them is described below.
To check code style on source codes we use [Checkstyle](https://checkstyle.sourceforge.io/). Currently, version 8.45.1
of Checkstyle is recommended.

Fortunately, Checkstyle has defined most of the rules needed to check Google code style in a file in
their [repo](https://github.com/checkstyle/checkstyle).
This [file](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml) is our
reference file to check Google code style on our codes with some customizations.

### Customizations applied on reference file:
1. **Severity is changed to 'error' instead of 'warning':** Code style issues on our code base are treated as blocker
issues and no code with checkstyle issues is allowed to be merged.

2. **The column width is changed from 100 to 120:** 
There were many multiline statements in our code base when we were applying the column limit of 100 characters. 
Working with a bit longer lines is easier and
developers need to wrap their lines less often. Although we have another requirement in mind: we want to see
a side-by-side diff view during code review process. In diff view, we do not want to have horizontal scrollbar
or line breaks. We think 120 column width is a good choice. Now most monitors, support the resolution
required to see two pages of 120 characters side-by-side.

3. **The indentation properties are all doubled:** That's not a big deal, but historically we have a lot of code 
written with block indentation of 4 spaces. We decided to stick to our old convention although Google suggests 2 spaces.

4. **MissingJavadocMethod rule is disabled:** This rule forces all developers to write Javadoc for all public methods
but as stated in Google code style, writing Javadoc for self-explanatory or obvious methods is not needed.

5. **SummaryJavadoc rule is disabled:** Sometimes we want to only explain an input argument of a method, or we want to
just explain the thrown exceptions. Forcing developers to write summary for all of Javadocs will move their focus
from important points to writing a summary to pass the checkstyle. 

6. **AvoidUnusedImports rules is added:** Although this is not part of the Google Checkstyle,
it has been added because it cleans the header of Java files by removing misleading references.

7. **MissingJavadocType rule is ignored on test files:** Usually test files do not require javadoc as it is obvious 
what class this test is for.

7. **Suppression file(if exists) must be located beside the main file**.