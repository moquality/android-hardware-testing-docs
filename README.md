Android Hardware Documentation
==============================

# [Docker Setup](/docker-setup.md)
# [Configuration Setup](/config-setup.md)





# [Working with Testlink](/testlink.md)
A current version of testlink is hosted at http://tl.moquality.com (username: archertest, password: testlink). Test cases are pre-loaded and can be viewed in Test Specification tab. 

![Testlink Build/Release Page](testlink.png)

- Create a Build using Build/Releases tab on the right. The build name has to be mentioned in the config file as well.
- After creating a Build, an administrator must assign the test cases to a user. Assigning test cases is done using Assign Test Case Execution.
- Test cases are executed automatically by our program. It checks periodically if there are any new tests assigned.
- In the report, a user can see the details of the substeps for each test case. If all the test cases are executed correctly, the test case is passed.

## Example Output from a Test Case

![Testlink Output](output.png)
