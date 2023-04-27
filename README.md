# E3-W3-U2--Git

1. create and move to a new branch:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git checkout -b newBranch
    Switched to a new branch 'newBranch'

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git branch
      master
    * newBranch

2. Create a commit on a branch:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git add .

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git commit -m 'adds sysout in ApplicationRunner'
    [newBranch c25a66d] adds sysout in ApplicationRunner
     1 file changed, 1 insertion(+), 1 deletion(-)

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git status
    On branch newBranch
    nothing to commit, working tree clean

3. Merge new branch on master:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git checkout master
    Switched to branch 'master'
    Your branch is up to date with 'origin/master'.

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git merge newBranch
    Updating a643ede..c25a66d
    Fast-forward
     .../java/it/epicode/be/prenotazioni/common/util/AppStartupRunner.java   | 2 +-
     1 file changed, 1 insertion(+), 1 deletion(-)

4. Create conflict between two branches:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git add .

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git commit -m 'conflictual commit on master'
    [master 12607a7] conflictual commit on master
     1 file changed, 1 insertion(+)

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git checkout newBranch
    Switched to branch 'newBranch'

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git add .

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git commit -m 'conflictual commit on newBranch'
    [newBranch 49a0ea6] conflictual commit on newBranch
     1 file changed, 1 insertion(+)

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (newBranch)
    $ git checkout master
    Switched to branch 'master'

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git merge newBranch
    Auto-merging src/main/java/it/epicode/be/prenotazioni/common/util/AppStartupRunner.java
    CONFLICT (content): Merge conflict in src/main/java/it/epicode/be/prenotazioni/common/util/AppStartupRunner.java
    Automatic merge failed; fix conflicts and then commit the result.

5. Fix conflict and complete merge:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master|MERGING)
    $ git add src/main/java/it/epicode/be/prenotazioni/common/util/AppStartupRunner.java

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master|MERGING)
    $ git commit -m 'fixed conflict'
    [master a1fdfe4] fixed conflict

    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git merge newBranch
    Already up to date.
    
6. Delete branch after merge:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git branch -d newBranch
    Deleted branch newBranch (was 49a0ea6).

7. Create a new Tag:
    *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
    $ git tag -a v1.1.0 -m 'adds importants system out'

8. Visualize commits log:
    Ale-O@PC-Onta MINGW64 ~/Documents/EpicodeJava/E3-W3-U2--Git (master)
    $ git log
    commit a1fdfe4307145fe4578cab2bb95b25667e3a1218 (HEAD -> master, tag: v1.1.0)
    Merge: 12607a7 49a0ea6
    Author: Alessandro <114835798+****@users.noreply.github.com>
    Date:   Thu Apr 27 15:30:10 2023 +0200

        fixed conflict

    commit 49a0ea6db9ea591ec0a317ee646c4d59a348d0f2
    Author: Alessandro <114835798+****@users.noreply.github.com>
    Date:   Thu Apr 27 15:23:46 2023 +0200

        conflictual commit on newBranch

    commit 12607a7445dbe1b0f8c2341d3a7063a4b6e5aacb
    Author: Alessandro <114835798+****@users.noreply.github.com>
    Date:   Thu Apr 27 15:22:46 2023 +0200

        conflictual commit on master

    commit c25a66dcce3cade2acc24fc706cca3ba49f9b631
    Author: Alessandro <114835798+****@users.noreply.github.com>
    Date:   Thu Apr 27 15:17:33 2023 +0200

        adds sysout in ApplicationRunner

    commit a643ede0d3b9b6b7c0f5ac2763d5aecea21ab3f3 (origin/master)
    Author: Alessandro <114835798+****@users.noreply.github.com>
    Date:   Thu Apr 27 15:09:07 2023 +0200

        initialized project

9. git pull:
      *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
      $ git pull
      remote: Enumerating objects: 6, done.
      remote: Counting objects: 100% (6/6), done.
      remote: Compressing objects: 100% (5/5), done.
      remote: Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
      Unpacking objects: 100% (5/5), 2.31 KiB | 337.00 KiB/s, done.
      From https://github.com/AleOnta/E3-W3-U2--Git
         a643ede..1837615  master     -> origin/master
      Merge made by the 'ort' strategy.
       README.md | 124 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
       1 file changed, 124 insertions(+)
       create mode 100644 README.md

      *************** ~/****/EpicodeJava/E3-W3-U2--Git (master)
      $ git push
      Enumerating objects: 61, done.
      Counting objects: 100% (51/51), done.
      Delta compression using up to 12 threads
      Compressing objects: 100% (24/24), done.
      Writing objects: 100% (39/39), 2.67 KiB | 911.00 KiB/s, done.
      Total 39 (delta 14), reused 0 (delta 0), pack-reused 0
      remote: Resolving deltas: 100% (14/14), completed with 5 local objects.
      To https://github.com/AleOnta/E3-W3-U2--Git.git
         1837615..ad47439  master -> master
