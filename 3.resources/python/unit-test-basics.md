### unittest
The unittest framework in Python expects tests to be organized in a specific way. By using a class that inherits from unittest.TestCase, you get access to many helpful features:
- Better test discovery (the framework can auttomatically find and run your tests)
- Built-in setup and teardown methods for test fixtures
- More specific assertion methods with better error messages

### __eq__ or assert
When comparing custom objects like Textnodes, a direct == comparison (which assert uses) won't work unless you've implemented the `__eq__` method. 

### Execution
With `unittest.main()` , you get automatic test discovery and execution, plus a summary of which tests passed or failed. 

### Isolated Tests
Creating each test in its own method, so if one test fails, the others will still run, giving you more information about what's working and what isn't

### Failure messages
When a test fails, unittest provides a detailed information about what was expected vs. what was received, making debugging easier. 
