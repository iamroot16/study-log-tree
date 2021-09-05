# IAMROOT16 Linux Kerenel v5.1 study log tree

[study log tree](https://rawcdn.githack.com/iamroot16/study-log-tree/main/README.html)

Use [rawcdn](https://rawcdn.githack.com/)

## git log example

Search include mm/vmscan.c file commit history.

```bash
$ git log --oneline --shortstat --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cs) %C(bold blue)<%an>%Creset' --abbrev-commit --before="2019-05-20" --after="2008-10-01"  --full-diff mm/vmscan.c
```

Search commit history that include mm/vmscan.c and changed 100 lines above.

```bash
$ git log --oneline --shortstat --pretty=format:'@ %Cred%h%Creset %Cgreen(%cs) %C(yellow)%d%Creset %s %C(bold blue)<%an>%Creset' --abbrev-commit --before="2019-05-20" --after="2008-10-01" --full-diff mm/vmscan.c | awk '$4 > 100 {print ;}' | tr "\n" " "  | tr "@" "\n" | grep insertions
```

Search vmscan.c::shrink_page_list() function releated commit history and print to text file.

```bash
$ git log --oneline --shortstat --pretty=format:'@ %Cred%h%Creset %Cgreen(%cs) %C(yellow)%d%Creset %s %C(bold blue)<%an>%Creset' --abbrev-commit --before="2019-05-20" --after="2008-10-01" -G shrink_page_list mm/vmscan.c > ~/commit.txt
```
