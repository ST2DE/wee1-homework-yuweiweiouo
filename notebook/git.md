# git �`�Ϋ��O

�ζ��`�`�ݭn�����ΦX�� branch�A���U�O�`�� git ���O

## git pull

�Գ̷s�� `master` �{���X��ثe branch�C���ެO�b���� branch ���O���橳�U���O

```
$ git pull --rebase origin master
```

## git reset

�o�e Pull Request ��A�S�ݭn�ק�ثe Branch �{���A�е��� git reset �Ӧ^��e�@�� commit ����

```
$ git reset --soft HEAD^
```

`HEAD^` �N��^��W�@�� commit�A�p�G�n�^��h�� commit �Х� `HEAD~4`�A�䤤 `4` �д����z�n���Ʀr

## git branch

�ΨӬݥثe������ branch �Ϊ̬O�j��R���a���� branch

```
$ git bracnch -D xxxx
```

`-D` �O�j��R��

## git checkout

�ΨӤ��� branch

### �����컷�� branch

�n review �O�H�� pull request�A�ШϥΩ��U���O

```
# Ū���̷s�� origin �{���X
$ git fetch origin
$ git checkout -b test origin/test
```

�o�˴N�i�H�����컷�� test branch �~��ާ@

### ��¤��� local branch

```
$ git checkout master
```

## git rebase

�b PR ���X�֦h�� commit ���e�A�o�O�Φb Code Review ������A��@�̷s�W�h�� commit�A�ݭn�N���� commit �X���@�� 

```
$ git rebase -i commit_id
```

���U�O�`�Ϊ����p

```
f, fixup = like "squash", but discard this commit's log message
s, squash = use commit, but meld into previous commit
```

��n squash �� commit id �e�����令 `f`�A�M�� `:wq` �s�ɡC�J��Ĭ�ѨM��A�i�H�U

```
$ git add xxxx
$ git rebase --continue
```

�n���X git rebase ���ܡA�ФU

```
$ git rebase --abort
```