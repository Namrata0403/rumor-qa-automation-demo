# Getting started with Rumor

# Technical Evaluation Test For QA Engineer

## Table of Contents
- [Task 1: Write Test Scripts](#task-1-write-test-scripts)
  - [About Candidate Project](#about-candidate-project)
  - [Setup Guide](#setup-guide)
  - [Testing Approach](#testing-approach)
- [Task 2: Debugging Challenge](#task-2-debugging-challenge)
  - [Analysis and Solutions for Handling Flaky Tests](#analysis-and-solutions-for-handling-flaky-tests)
- [Overall Contributions](#overall-contributions)

## Task 1: Write Test Scripts

### About Candidate Project
**AGROWORLDS**  
AGROWORLDS empowers SSI Agroworld, a leading agricultural commodities broker and trader, to tackle challenges in the international trade market. It provides an internal automation platform that streamlines daily tasks and workflows, allowing SSI Agroworld to operate more effectively. The application is focused on eliminating problems faced in the International trade market around Agricultural commodities by providing automation solutions to the internal team for daily activities and tasks.

### Setup Guide

#### Prerequisites
- Java Development Kit (JDK) – Version 17: [Download JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
- Maven - Dependency management: [Download Maven](https://maven.apache.org/download.cgi)
- Selenium WebDriver - For browser automation: [Download Selenium](https://www.selenium.dev/downloads/)

#### Installation Steps (Windows)
1. **Clone the repository**
git clone <repository-url>

2. **Install Maven on your system**
- Find Your Maven Installation Directory:  
  For example, if you extracted Maven to `C:\Program Files\apache-maven-3.9.6`, then that's your Maven installation directory.
- Edit the System Environment Variables:
  - Update the PATH Variable:
    - In the Environment Variables window, under the "System variables" section, find the Path variable and select it.
    - Click "Edit".
    - In the Edit Environment Variable window, click "New" and add the path `C:\Program Files\apache-maven-3.9.6\bin` to the bin directory of your Maven installation.
- **Verify the Maven Installation:**
  ```
  mvn -v
  ```
3. **Run the Tests**
mvn test



### Testing Approach
Our data-driven test framework simplifies test maintenance and allows for easy updates as the application changes.

## Task 2: Debugging Challenge

### Analysis and Solutions for Handling Flaky Tests
As we know, Flaky tests are automated tests that exhibit both passing and failing outcomes under the same configuration.

**Common Causes and Proposed Solutions:**
- **Cause 1:** Asynchronous operations can cause flaky tests if elements are interacted with before they're loaded.
- **Solution:** Use explicit waits (e.g., WebDriverWait) to ensure elements are in the desired state before interaction.
 ```java
 WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
 wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("someElementId")));
 ```
- **Cause 2:** UI changes (identifiers, layouts, styles) can break tests with fragile selectors.
- **Solution:** Prioritize stable identifiers (id, data-test-id) and avoid complex XPath selectors. Collaborate with developers to ensure critical elements are identifiable for testing.
- **Cause 3:** Test order dependencies can cause flakiness in parallel execution.
- **Solution:** Design tests to be independent, avoiding reliance on specific execution order.
- **Cause 4:** Environmental differences (browsers, APIs, dependencies) can cause test flakiness.
- **Solution:** Regularly update tests to reflect the application's current state. Integrate tests into CI for consistent execution.

## Overall Contributions
- Developed a robust data-driven test framework (Java, Selenium, TestNG) for AGROWORLD's app.
- Leveraged Apache POI for data management and explicit waits for asynchronous content, resulting in reliable and maintainable tests.
- Resolved issues around test flakiness by implementing solutions for page load handling issues and prioritizing stable identifiers.
- Demonstrated proficiency in key QA tools (Java, Selenium, TestNG, Github, Jenkins), creating a flexible and resilient testing environment, adaptable to application updates and UI changes.
- Documented solutions and shared practical steps for transparent knowledge transfer.

## Test Execution Recording Videos

- **Test Execution through Eclipse**: [Watch the video here](https://drive.google.com/file/d/1-S93Pm0dTS6eN6XJVKg1d2ZYkPBu7g8A/view?usp=sharing)
- **Test Execution through Maven commands**: [Watch the video here](https://drive.google.com/file/d/11ug3HpVXMhI2hCb0bONJPci3Vlg6ldi0/view?usp=sharing)