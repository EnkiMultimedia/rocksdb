# barrel-db/rocksdb

This repository is [erlang-rocksdb]'s fork of [RocksDB], a persistent key-value
store for fast storage.

It exists for two reasons: to provide a home for Erlang-specific patches,
as necessary, and to ensure that RocksDB subtree in
[barrel-db/erlang-rocksdb][erlang-rocksdb] has a controlled remote to point
at.

⚠️ It is critical that any commit in this repository that is referenced from
[barrel-db/erlang-rocksdb][erlang-rocksdb] remains available here in perpetuity. For
every referenced commit, there must be at least one named branch or tag here
that has the commit as an ancestor, or else the commit will be garbage collected
by GitHub/Gitlab.

## To update erlang-rocksdb

  1. add `rocksdb` as a remote : 

  ```shell
  git remote add -f rocksdb https://gitlab.com/barrel-db/Deps/rocksdb.git
  ```

  2. Updte the project to last release X.X.X.erl

  ```shell
  git fetch rocksdb X.X.X.erl
  git subtree pull --prefix deps/rocksdb rocksdb X.X.X.erl --squash
  ```

  3. push the change to origin

  ```shell
  git push origin BRANCH
  ``` 

See the [atlassian doc](https://www.atlassian.com/blog/git/alternatives-to-git-submodule-git-subtree)
 for more informations.

> note: to create the initial folder as a subtree we run the command line :
>
> ```shell
> git subtree add --prefix deps/rocksdb rocksdb X.X.X.erl --squash
> ```


## To create a new release branch:

  1. Follow step one above.

  2. Add an upstream remote and fetch from it.

     ```shell
     $ git remote add upstream https://github.com/facebook/rocksdb
     $ git fetch upstream
     ```

  3. Create and push a new branch with the desired start point:

     ```shell
     $ git checkout -b X.X.X.erl RELEASE-TAG
     $ git push origin X.X.X.erl
     ```

  4. Protect the branch from force-pushes in the repository settings. This is
     crucial in ensuring that we don't break commit references in
     [barrel-db/erlang-rocksdb][erlang-rocksdbb]'s submodules.

  5. Follow steps three through six above.

[erlang-rocksdb]: https://github.com/barrel-db/erlang-rocksdb
[RocksDB]: https://github.com/facebook/rocksdb 
