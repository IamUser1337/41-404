Comprehensive test scenarios should be directly related to findings during the planning and designing phases that were covered in previous modules.

The first step is to write the unit tests. Make sure that you classify the tests by each feature or function. The test cases for unit tests should be listed similar to the following table.

|      Test case No.     |      Description of    test      |      Inputs to test    with      |      Expected result                                                                   |      Result     |
|------------------------|----------------------------------|----------------------------------|----------------------------------------------------------------------------------------|-----------------|
|     1-1                |     Next Service Available       |     Regulator Overhaul           |     Next available four-hour block is suggested                                           |                 |
|     1-2                |     Next Technician Available    |     Output from Test case 1-1    |     Technician available for that four-hour block is assigned to   the service request    |                 |
|     1-3                |     Suggested Products           |     Scubapro Hydros Pro          |     Three new products should be suggested                                                 |                 |
