# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > | When the code is ran, C# compiles it using the namespaces and executes them. The class names in a namespace wont clash with class names in other namespaces. |

02. What is the difference between a `class` and an `interface`?

  > | A class is designed so that its methods and declarations can be utilized by subclasses. They can also use constructors which interfaces cannot. An interface contain method declarations. |

03. What is the method that returns an instance of a class, yet it has no return type?

  > | void doesn't have a necessary return type or value.   |

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > | The access modifier is public. This makes the method available to use in other classes. |

06. In the Car example what is `string` an indication of?

  > | string indicates that what is being returned is a string. If it were not, the code would not be allowed to run. |

07. In the Car example what is `abstract` preventing?

  > | It is preventing itself from being re-instantiated. Its a class that can be used as a base for other common classes to inherit. |

08. In a SQL table, what is the difference between information in a row and information in a column?

  > | Information in the column is the key value pair. The row is the whole object containing key value pairs. |

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  > CREATE TABLE
  characters(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age VARCHAR(255) NOT NULL,
    description VARCHAR(255) NOT NULL
  )

10. In SQL how can you query more than a single table? Provide an example.

  > You must use JOIN in order to query more than one table at a time. EX:

  SELECT phones FROM store
  JOIN users ON phones.userId = users.id;
