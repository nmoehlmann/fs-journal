# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > | It allows a class to inherit methods and values from its parent class. And a class can have an endless line of children classes. However, C# does not allow for one class to have multiple child classes. |

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base ``?

  > | A class can extend another class which inherits almost everything in the parent class. Things that are not inherited are constructors and finalizers. |

3. How does ***accessibility*** affect inheritance?

  > | A private class or member cannot be seen or used in child classes. The only way for a child class to access these private methods / values is if its nested in the parent class. |

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > | A primary key lets SQL know that the associated value is the rows ID. SQL will separate table data by this primary key. Foreign keys are used to associate data in a row to a row in a separate table. |

5. What is an ***alias***?

  > | An alias is a banana word that we temporarily give to a row in a table.  |

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > | SELECT doc.*, pd.* FROM doctors JOIN patient_doctors doc.id = pd.doctorId
      WHERE doc.id = @doctorId |
