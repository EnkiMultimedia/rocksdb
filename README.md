# barrel-db/rocksdb

This repository is [erlang-rocksdb]'s fork of [RocksDB], a persistent key-value
store for fast storage.

It exists for two reasons: to provide a home for Erlang-specific patches,
as necessary, and to ensure that RocksDB subtree in
[barrel-db/erlang-rocksdb][erlang-rocksdb] has a controlled remote to point
at.

It is critical that any commit in this repository that is referenced from
[barrel-db/erlang-rocksdb][erlang-rocksdb] remains available here in perpetuity. For
every referenced commit, there must be at least one named branch or tag here
that has the commit as an ancestor, or else the commit will be garbage collected
by GitHub.

**To create a new release branch:**

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
