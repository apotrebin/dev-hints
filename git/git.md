### Git flow 

1. git checkout dev
2. git pull origin dev
3. git checkout -b <feature_branch>
4. git add .
5. git commit -m '<jira_ticket_key> add <feature_name>'
6. git push origin <feature_branch>

#### Before Pull/Merge Request
```
git checkout develop
git pull origin develop
git checkout <feature_branch>
git rebase develop
git push -f origin <feature_branch>
```