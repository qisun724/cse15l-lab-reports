# LAB REPORT 3 - RESEARCHING COMMANDS
grep command-line options or alternate ways to use the command

## 1. Line numbers of Matching Lines using `-n`
**Example 1:**   `$ grep -n "USA" technical/911report/*`
```
technical/911report/chapter-1.txt:28:    The security checkpoints through which passengers, including Atta and his colleagues, gained access to the American 11 gate were operated by Globe Security under a contract with American Airlines. In a different terminal, the single checkpoint through which passengers for United 175 passed was controlled by United Airlines, which had contracted with Huntleigh USA to perform the screening.
technical/911report/chapter-10.txt:158:                the USA PATRIOT Act) began to take shape.
technical/911report/chapter-13.4.txt:834:                Accordance with Section 359 of the [USA PATRIOT Act]"Nov. 2002; Treasury
technical/911report/chapter-13.5.txt:1074:                this strict interpretation remained in effect until the USA PATRIOT Act was passed
technical/911report/chapter-13.5.txt:2071:                Cauchon and Martha Moore,"Miracles Emerge from Debris," USA Today, Sept. 6, 2002, p.
technical/911report/chapter-13.5.txt:2382:                Appropriate Tools Required to Intercept and Obstruct Terrorism (USA PATRIOT ACT) Act
technical/911report/chapter-13.5.txt:2468:                DOS record, Log of USA 9-11 Terrorist Attack Task Force, Sept. 13, 2001; Jack S.
technical/911report/chapter-13.5.txt:3014:                106-215, 114 Stat. 337 (2000), � 2(a). The USA PATRIOT Act mandated that the
```
The `-n` command-line option prints out the line numbers of matching lines along with their matching lines as well to the terminal. This is useful as it allows us to skip straight to the line numbers in the files to read about the all the contents instead of reading it off of the terminal.\

**Example 2:**  `$ grep -n "journal" technical/plos/journal.pbio.0020001.txt technical/plos/journal.pbio.0020010.txt`
```
technical/plos/journal.pbio.0020001.txt:110:        which are mutually exclusive. It is possible that publishing in international journals as a
technical/plos/journal.pbio.0020001.txt:126:        journals (
technical/plos/journal.pbio.0020001.txt:129:        the 20 top ecological journals (with impact factors of 10.51–2.47) (ISI 2001a). We credited
technical/plos/journal.pbio.0020001.txt:134:        For the top 20 ecological journals, the American subcontinents of South, Central, and
technical/plos/journal.pbio.0020001.txt:138:        data as contributions to the top 10 ecological journals (impact factors 10.51–3.31) versus
technical/plos/journal.pbio.0020001.txt:140:        twice as many publications to journals in the second category (8% in the top 11–20 compared
technical/plos/journal.pbio.0020001.txt:142:        regions as Latin America are falling short of reaching the top journals. In contrast, the
technical/plos/journal.pbio.0020001.txt:143:        United States contributed somewhat more publications to the top 10 journals (84%) than the
technical/plos/journal.pbio.0020001.txt:144:        top 11–20 journals (79%). The difference in the proportion of publications contributed by
technical/plos/journal.pbio.0020001.txt:145:        the United States to the top 10 and top 20 journals was even more pronounced when we
technical/plos/journal.pbio.0020001.txt:147:        contributed 60% of the publications to the top 10 journals and only 40% of the publications
technical/plos/journal.pbio.0020001.txt:148:        to the top 11–20 journals.
technical/plos/journal.pbio.0020001.txt:152:        Nature were nearly identical to those of the top 20 ecological journals.
technical/plos/journal.pbio.0020001.txt:156:        versus 6% in the top 20 ecological journals, whereas the United States and Canada had 81%
technical/plos/journal.pbio.0020001.txt:158:        American researchers are not shying away from the two top-ranked general science journals.
technical/plos/journal.pbio.0020001.txt:168:        international journals, despite its robust productivity as measured by the number of
technical/plos/journal.pbio.0020001.txt:174:        the top journals or become amongst the most cited researchers in their fields? One
technical/plos/journal.pbio.0020001.txt:176:        and that the top journals, which are published in the developed world, respond more to the
technical/plos/journal.pbio.0020001.txt:180:        journals share a similar economic region, they also share the same perception of what
technical/plos/journal.pbio.0020001.txt:181:        science is most interesting to them. Another consideration is that more local journals from
technical/plos/journal.pbio.0020001.txt:182:        developed regions are listed by the SCI than similar journals from developing regions
technical/plos/journal.pbio.0020001.txt:226:        target the journals that have the greatest impact. Although there may still be a long road
technical/plos/journal.pbio.0020010.txt:11:        important journal runs JSTOR has digitised. Paper holdings have not decreased dramatically,
technical/plos/journal.pbio.0020010.txt:17:        Likewise, the decision to digitise the back-runs of around 100—now 218—paper journals was a
technical/plos/journal.pbio.0020010.txt:18:        bold decision at the time, but the future for access to journal literature lies in
technical/plos/journal.pbio.0020010.txt:24:        readers. As the number of journal articles accessible over the networks increases, JSTOR
technical/plos/journal.pbio.0020010.txt:35:        JSTOR's public image is of quality in depth—long runs of core journals—and that image has
technical/plos/journal.pbio.0020010.txt:42:        realised through their ‘Big Deals’ in selling hundreds of journals to hundreds of libraries
technical/plos/journal.pbio.0020010.txt:52:        publishers do not have to sell their product to users of their journals, but local
technical/plos/journal.pbio.0020010.txt:56:        America and Western Europe to be published in peer-reviewed open-access journals more
technical/plos/journal.pbio.0020010.txt:57:        readily than in the traditional subscription-based journals.
```
If we want to quickly compare if two files have similar content, like checking for playgiarism, we can use grep -n on the two files to know where the similar content start via the line number. Similarly, we can use this command-line option on java files instead of text files to quickly find the lines of code we need, such as finding specific methods to look at their implementation, and even comparing the different implementations. 

I remember seeing this option somewhere online, so I asked ChatGPT with the given prompt to know more about it: what uses can I do with grep -n.\



## 2. Count of Appearances using `-c`
**Example 1:**   `$ grep -c "Hungerford" technical/government/Alcohol_Problems/DraftRecom-PDF.txt `
```
13
```
The `-c` command-line option gives the number of times the provided pattern appears in the file(s), and in this case, the number of times "Hungerford" appears in the DraftRecom-PDF.txt is 13. This can be useful if we want to count the number of error messages in our file.\

**Example 2:**   `$ grep -c "^" technical/911report/*.txt`
```
technical/911report/chapter-1.txt:731
technical/911report/chapter-10.txt:603
technical/911report/chapter-11.txt:817
technical/911report/chapter-12.txt:1539
technical/911report/chapter-13.1.txt:1089
technical/911report/chapter-13.2.txt:1236
technical/911report/chapter-13.3.txt:1718
technical/911report/chapter-13.4.txt:2941
technical/911report/chapter-13.5.txt:3237
technical/911report/chapter-2.txt:948
technical/911report/chapter-3.txt:3159
technical/911report/chapter-5.txt:1204
technical/911report/chapter-6.txt:1898
technical/911report/chapter-7.txt:1579
technical/911report/chapter-8.txt:1036
technical/911report/chapter-9.txt:1885
technical/911report/preface.txt:108
```
This use of the command-line option is counting the number of lines in all the text files inside the 911report directory. We can even put all that result in a new file and sort it so it can be useful if we want to know which files has the most lines/content. This behaves similar to the `wc` command.

The sources I used for this command-line option is the website [Grep Command in Linux](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/) and ChatGPT with the prompt "different ways to use grep -c".\




## 3. Name of Files using `-l`
**Example 1:**   `$ grep -l "Utah" technical/government/Media/*.txt`
```
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/All_May_Have_Justice.txt
technical/government/Media/Funding_May_Limit.txt
technical/government/Media/It_Pays_to_Know.txt
technical/government/Media/Supporting_Legal_Center.txt
technical/government/Media/The_State_of_Pro_Bono.txt
technical/government/Media/grants_fail_to_come.txt
```
The `-l` command-line option gives us the path/name of files that contain the given pattern, which in this case, the above are the paths of files that contain "Utah". This is useful if we want to know the paths of files with specific content, which could also be used if we want to check if all files have a certain method when working with java files.

**Example 2:**   `$ grep -l "microorganisms" technical/plos/*.txt | xargs cat`
```
 
    
      
        
        For half a century, natural products from microorganisms have been the main source of
        medicines for treating infectious disease. The most important chemical class of these
        antibiotics, apart from the penicillins, is the polyketides. They are made by the stepwise
        building of long carbon chains, two atoms at a time, by multifunctional enzymes that
        determine the chain length, oxidation state, and pattern of branching, cyclisation, and
        .
        .
        .
        difficulties in production that have led to shortages since licensure. A better
        understanding of the mechanisms that underlie natural immunity to pneumococcus could pave
        the way for the development of more effective, species-specific pneumococcal vaccines.
      
    
      
```
If we want to find a file that mentions a certain topic in a directory, we can use this command-line option, such as shown above where we found the path of the file about microorgnisms, give it as the input for cat to print the content to the terminal to brief read. This command can also be used if we want to quickly look at the implementation of certain methods.

I learned about this command-line option in the [Linux Pocket Guide by Daniel J. Barrett](https://www.oreilly.com/library/view/linux-pocket-guide/9780596806347/re52.html).




## 4. Ignore Cases Using `-i`
**Example 1:**   `$ grep -i "USA" technical/911report/*`
```
```
What it is doing and why it is useful

**Example 2:**   `$ grep -n "USA" technical/911report/*`
```
```
What it is doing and why it is useful

cite sources
