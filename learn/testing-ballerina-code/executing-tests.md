---
layout: ballerina-left-nav-pages
title: Executing Tests
description: Learn how to use different options for executing Ballerina tests.
keywords: ballerina, programming language, testing
permalink: /learn/testing-ballerina-code/executing-tests/
active: executing-tests
intro: The sections below include information about executing tests in Ballerina.
redirect_from:
  - /v1-2/learn/testing-ballerina-code/executing-tests
  - /learn/testing-ballerina-code/executing-tests
---

## Executing Tests Using CLI Commands

Tests will be automatically executed when you run the build command or you can explicitly run them using the test command. 

Execute tests within the specified module with the following command.

```
$ ballerina test <module_name>
```

Execute tests in the entire project using the --all option.

```
$ ballerina test --all
```

List all test groups in a given module.

```
$ ballerina test --list-groups <module_name>
```

Run only the tests belonging to the given group(s) in the current project.

```
$ ballerina test --groups <group_1>,<group_2>  --all
```

Run the tests in the current project excluding the given group(s).

```
$ ballerina test --disable-groups <group_1>  --all
```

Run only the given test function(s) in the current project.

```
$ ballerina test --tests <test_function> --all
```

Generate an HTML test report.

```
$ ballerina test --test-report <module-name> | -a | --all
```

Generate the HTML test report with code coverage information.

```
$ ballerina test --code-coverage <module-name> | -a | --all
```

For more options of the test command, run the following.

`$ ballerina test --help` 


## Test Report

By default, a summary of the test statuses is printed in the console at the end of the test execution. In addition to the results printed in the console, an HTML test report can be generated by passing the `--test-report` flag in the Ballerina command. The link to the file will be printed in the console at the end of the test execution.

The test report contains the total passed, failed, and skipped tests of the entire project and of the individual modules.

***Example:***

```
$ ballerina test --test-report --all
```

A sample view of the test report is shown below.

![Sample Test Report](/learn/images/test-report.gif)

## Code Coverage Report

The Ballerina test framework provides an option to analyze the code coverage of a standard Ballerina project. This feature provides details about the coverage of the program source code by the tests executed. 

You can pass the `--code-coverage`  flag in the test execution command and generate the code coverage report  at the end of the test execution. The generated file is an extended version of the test report. In addition to the test results, this file would contain details about the source code coverage in different levels.

*   Project-level coverage as an average
*   Module-level coverage as an average
*   Individual source file coverage

The code coverage only includes the Ballerina source files being tested and not any files under the **_tests/_** directory.

***Example:***

```
$ ballerina test --code-coverage --all
```

A sample view of the code coverage report is shown below.

![Sample Code Coverage](/learn/images/code-cov.gif)