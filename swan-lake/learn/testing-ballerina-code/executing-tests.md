---
layout: ballerina-left-nav-pages-swanlake
title: Executing Tests
description: Learn how to use different options for executing Ballerina tests.
keywords: ballerina, programming language, testing
permalink: /swan-lake/learn/testing-ballerina-code/executing-tests/
active: executing-tests
intro: The sections below include information about executing tests in Ballerina.
redirect_from:
  - /swan-lake/learn/testing-ballerina-code/executing-tests
---

## Executing Tests Using CLI Commands

Tests will be automatically executed when you run the build command or you can explicitly run them using the test command. 

Execute all the tests in the current package with the following command.

```
$ ballerina test
```

List all the test groups in the package.

```
$ ballerina test --list-groups
```

Run only the tests belonging to the given group(s) in the current package.

```
$ ballerina test --groups <group_1>,<group_2>
```

Run the tests in the current package excluding the given group(s).

```
$ ballerina test --disable-groups <group_1>
```

Run only the given test function(s) in the current package.

```
$ ballerina test --tests <test_function>
```

Run only the previously-failed test cases in the current package.

```
$ ballerina test --rerun-failed
```

Generate an HTML test report.

```
$ ballerina test --test-report
```

Generate the HTML test report with code coverage information.

```
$ ballerina test --code-coverage
```

For more options of the test command, run the following.

`$ ballerina test --help` 

## Test Report

By default, a summary of the test statuses is printed in the console at the end of the test execution.
In addition to the results printed in the console, an HTML test report can be generated by passing the `--test-report` flag in the Ballerina command. The link to the file will be printed in the console at the end of the test execution.
The test report contains the total passed, failed, and skipped tests of the entire package and of the individual modules.

***Example:***

```
$ ballerina test --test-report
```

A sample view of the test report is shown below.

![Sample Test Report](/swan-lake/learn/images/test-report.gif)

## Code Coverage Report

The Ballerina test framework provides an option to analyze the code coverage of a standard Ballerina package.
This feature provides details about the coverage of the program source code by the tests executed.

You can pass the `--code-coverage`  flag in the test execution command and generate the code coverage report at the end of the test execution. The generated file is an extended version of the test report.
In addition to the test results, this file would contain details about the source code coverage in different levels.

*   Package-level coverage as an average
*   Module-level coverage as an average
*   Individual source file coverage

The code coverage only includes the Ballerina source files being tested and not any files under the **_tests/_** directory.

***Example:***

```
$ ballerina test --code-coverage
```

A sample view of the code coverage report is shown below.

![Sample Code Coverage](/swan-lake/learn/images/code-cov.gif)