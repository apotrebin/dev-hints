### Git flow 

1. git checkout dev
2. git pull origin dev
3. git checkout -b <feature_branch>
4. git add .
5. git commit -m '<jira_ticket_key> add <feature_name>'
6. git push origin <feature_branch>

#### Before Pull/Merge Request
```
git checkout dev
git pull origin dev
git checkout <feature_branch>
git rebase dev
git push -f origin <feature_branch>
```

Note:
Во время ребейза могут возникнуть конфликты. В таких случаях процесс ребейза останавливается до их разрешения. После того, как все конфликты будут разрешены, процесс ребейза можно продолжить командой:
- ```git rebase --continue```
Также, можно прервать процесс и вернуться на состояние до начала ребейза:
- ```git rebase --abort```

#### When PR/MR has merged
- ```git branch -d <feature_branch>```