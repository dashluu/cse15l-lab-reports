# Week 5 Lab Report
**Author**: Trung Dat Luu.<br>
In this week's lab report, I have chosen `find` as my command to do research on.
# Find -name
## Usage
* `find -name pattern` finds files whose name match the pattern in `pattern`.
* This command-line option is specifically useful if the user wants to look for files that have names matching a regular expression.
## Examples
### Example 1
```
> find ./technical -name "Med*"
./technical/government/Media
```
In example 1, the command looks for files that start with `Med*` and returns `./technical/government/Media` as the only result.
### Example 2
```
find ./technical -name "journal*01.*"
./technical/plos/journal.pbio.0020001.txt
./technical/plos/journal.pbio.0020101.txt
./technical/plos/journal.pbio.0020401.txt
```
In example 2, `find -name` returns all files that start with `journal` and end with `01` and whose extensions can be anything, expressed by the symbol `*`.
### Example 3
```
find ./technical -name "chapter-[0-9].*"
./technical/911report/chapter-1.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
```
In this example, `find -name` looks for files that start with `chapter-` followed by one numeric value (0 to 9) with a wildcard extension.
# Find -size
## Usage
* `find -size (+/-)n` finds files whose sizes are less than, equal, or larger than `n`.
* This command-line option is useful if the user wants to find all files that have sizes within a given range.
* There are 6 options to specify file sizes: `b` for 512-byte blocks, `c` for bytes, `w` for two-byte words, `k` for kibibytes (1024 bytes), `M` for mebibytes (1024^2 bytes), and `G` for gibibytes(1024^3 bytes).
## Examples
### Example 1
```
> find ./technical -size +100k
./technical/911report/chapter-1.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/biomed/1471-2105-3-2.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/d0269g.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/government/Gen_Account_Office/gg96118.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/im814.txt
./technical/government/Gen_Account_Office/May1998_ai98068.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```
In this example, the find command is used to find all files that are larger than 100 kibibytes.
### Example 2
```
> $ find ./technical -size +100k -size -200k
./technical/911report/chapter-1.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/biomed/1471-2105-3-2.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d0269g.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/government/Gen_Account_Office/gg96118.txt
./technical/government/Gen_Account_Office/im814.txt
./technical/government/Gen_Account_Office/May1998_ai98068.txt
./technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
```
In this example, the find command with the `-size` option is used to find all files that have sizes more than 100 kibibytes but less than 200 kibibytes.
### Example 3
```
> find ./technical -size 50k
./technical/biomed/1471-2156-3-17.txt
./technical/biomed/1472-684X-1-5.txt
./technical/biomed/gb-2001-2-8-research0030.txt
./technical/biomed/gb-2002-3-5-research0025.txt
./technical/government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
```
In this example, `find -size` returns all files with 50 kibibytes of space, rounding up.
# Find -mmin
## Usage
* `find -mmin (+/-)n` finds files that were modified less than, exactly, or more than `n` minutes ago, which is useful if the user wants to look for files that were changed during a given period of time.
## Examples
### Example 1
```
> find ./technical -mmin -1
./technical
./technical/government/Media/5_Legal_Groups.txt
```
In example 1, `find -mmin -1` finds all the files that have been modified within the last 1 minute.
### Example 2
```
> find ./technical -mmin +2
./technical/911report
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
...
```
In example 2, `find -mmin +2` finds all the files that have been modified more than 2 minutes ago.
### Example 3
```
> find ./technical -mmin 1
./technical/government/Media/A_helping_hand.txt
```
In example 3, `find -mmin 1` finds all the files that have been modified exactly 1 minute ago.