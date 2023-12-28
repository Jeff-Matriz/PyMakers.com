---
title: "A Whirlwind Journey into C#: Tackling String Manipulation Challenges in a Day!"
date: 2023-12-21
---

**Introduction:**
Greetings, fellow learners and coding enthusiasts! Today, I'm thrilled to share my whirlwind experience of diving into the world of C# in just a day. Imagine this: a job opportunity knocks, and it requires proficiency in C#. Challenge accepted, right? So, buckle up as I take you through my exhilarating ride of conquering C# challenges and the unexpected twists it threw my way.

**The First Challenge: Unleashing Creativity in String Manipulation!**

The first challenge was all about string manipulation - a seemingly simple task, but with a delightful twist. Picture this: the user inputs a sentence, and the challenge is to replace a certain word within that sentence. Easy, right? Not quite! Here's the kicker: the use of `Replace` and `Length` is off-limits. Time to get creative!

 Armed with my budding knowledge of C#, I resorted to arrays, `foreach` loops, and a dash of `for` loops. It was a maze of characters and logic, but in the end, I emerged victorious! The thrill of overcoming this challenge with my limited C# expertise was electrifying. Who knew string manipulation could be so exhilarating?

**The Unfinished Symphony: Strings, Rows, Columns, and a Dash of Creativity!**

The second challenge proved to be a bit elusive during the exam - strings, rows, columns, and a hint of mystery. The task was to generate an output based on user inputs: number of rows, number of columns, numbers per output, and page count. A puzzle that required a moment of reflection.

To give you an idea, here's how the output should look like:<br><br>
<img src="/assets/csharp-challenge.png" alt="The seconds C# challenge sample output." style="height: 400px; width: auto; display: block; margin: auto;">

Fast forward to my journey home, and the solution hit me like a bolt of lightning. In the comforting embrace of C#, I crafted a solution that danced across rows and columns. A symphony of loops played out - outer rows, inner rows, columns, and page labels. The code wove a tale of creativity, exploration, and problem-solving. If only it had been Python, I thought with a smile, but hey, where's the fun in a challenge without a bit of complexity?

Here's my solution to the problem:
```Csharp
using System;

namespace CSharpChallenge
{
  class Program
  {
    static void Main(string[] args)
    {
      int x = 1;
      int counter = 1;
      for(int i = 0; i < 5; i++) {                               // 5 outer rows = limit/(inner row x column)
        for(int j = 0; j < 5; j++) {                             // 5 inner rows
          if(x % 5 == 0) Console.Write(counter.ToString("000")); // page label
          for(int k = 0; k < 4; k++) {                           // 4 columns
              Console.Write("\t" + x.ToString("000"));
              x+=5;
          }
          x -= 19;                                              // x -= ((inner row x column) - 1)
          Console.WriteLine();
        }
        x += 15;                                                // (inner row x column) - inner row
        counter++;
        Console.WriteLine();
      }
    }
  }
}			// I didn't know about 'varName.ToString("000");' until I googled it (=
```

**The Joy of Coding Epiphanies:**

Isn't it fascinating how solutions can manifest when you least expect them? As I pondered the second challenge on my way home, the pieces fell into place. Coding epiphanies have this magical quality, appearing when you least anticipate them. It's the beauty of problem-solving and the joy that comes with connecting the dots.

**Conclusion:**

In the span of a day, C# went from a challenge to a thrilling adventure. String manipulations and creative problem-solving became my companions. The unexpected twists and turns added flavor to my coding journey. Who knew that in the world of coding, thinking outside the box could lead to triumphs and the joy of unraveling complex problems? Here's to the beauty of coding surprises and the excitement of conquering new challenges. Happy coding, fellow learners! 🚀🎉

I also got my certification as a C# learner with FCC and Microsoft, checkout my updated portfolio: <a href="https://www.pymakers.com/jeff/" target="_blank">Foundational C# with Microsoft</a>