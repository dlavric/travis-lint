# Repository to test the .travis.yml file with 'lint' for errors

## How to use this repo

- Clone this repo:
```shell
$ git clone https://github.com/dlavric/travis-lint.git
```

- Go to the directory of the repository:
```shell
$ cd travis-lint
```

- Test the .travis.yml with lint:
```shell
$ travis lint
```

Output:
```shell
Hooray, .travis.yml looks valid :)
```

## Different ways to test 'lint' with .travis.yml file

- Provide a path to a different file:
```shell
$ travis lint ~/Downloads/dlavric/TestTravis/.travis.yml
```

- Pipe the content of a .travis.yml file:
```shell
$ echo "dist: bionic" | travis lint
```

Output:
```shell
Hooray, STDIN looks valid :)
```

- Echo a message if Travis doesn't validates:
  - use -q to suppress any output; 
  - use -x to have it set the exit code to 1 if there are  any warnings;
```shell
$ travis lint ~/Downloads/dlavric/TestTravis/.travis.yml || echo ".travis.yml doesn't validate"
```

Output:
```shell
.travis.yml doesn't validate
```