# Invoke-LambdaFunction-with-another-LambdaFunction
## What will we be using?
1.IAM Role

2.Lambda Functions

3.Python 

## Set Up Steps

1. On the AWS Console, Navigate to IAM

<img width="1432" alt="step 1" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/deb866fc-96cd-40e7-9170-fb6fa9b8322f">

2. Select roles on the left hand side

<img width="1432" alt="step 2" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/ad6f206e-f9be-485a-be3e-6f42281a0fa1">

3. Select create role

<img width="1432" alt="step 3" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/e12158cf-fb57-418f-9c32-6b8490834044">

4. Under use case, select Lambda followed by next at the bottom.

<img width="1432" alt="step 4" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/55d2d6da-acd1-4ac7-9360-80aa92a37590">

5. Under permissions, we want to add 2 policies. The first policy is cloudwatchlogs

<img width="1432" alt="step 5" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/43663b90-a796-48ca-8a2b-55c2d6ddfe84">

6. For your 2nd policy, add AWSLambda_Full Access Permissions. Select next at the bottom

<img width="1432" alt="step 6" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/5c8de799-1481-4b8a-bb88-f87254768ab8">

7. Give your role a name like LambdaTriggerLambdaRole followed by create at the bottom.

<img width="1432" alt="step 8" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/c2890890-5181-42f0-b23a-d3a3f11bdd49">

8. Navigate to Lambda on the AWS Console

<img width="1432" alt="step 9" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/d18948d5-f26b-4b03-8f0a-215d3853d072">

9. Select create function and give it a name like LambdaNumberOne. In the runtime section, select your latest version of Python, and select ARM64 in the Architecture section.

<img width="1432" alt="step 9" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/563b2932-a2da-43e4-af19-4d787da6ee23">

10. Under role, choose Use existing role and select the role we created earlier (LambdaTriggerLambdaRole) then select create

<img width="1432" alt="step 10" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/7a86b466-2224-4f12-aa93-b1d51a12c2a4">

11. Once created, select configuration, select edit, and change the timeout to 1 minute follow by save.

<img width="1432" alt="step 11" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/fe81e52b-b77e-442d-a232-fb14ea3d6412">

12. Navigate back to Lambda and create a second Lambda Function using the same steps as above.

<img width="1432" alt="step 12" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/406e6995-a853-44b0-9cd3-0e6402ae6e9f">

13. Head back over to LambdaNumberOne and select code and use the following code below which will help send a message to LambdaNumberTwo

<img width="1432" alt="step 13" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/3293d544-6e59-488d-a974-40f8ed04c8f3">

14. Navigate to LambdaNumberTwo and write the code below

<img width="1432" alt="step 14" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/acfe4989-98c3-44e6-a0f1-ef9492fedaaf">


15. Once completed, head back to LambdaNumberOne, select deploy, followed by test and give your test a name with the appropriate JSON texts.

<img width="1432" alt="step 15" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/97d7b08d-d357-4c00-9134-6de15debff73">

16. Once completed, select test and you should see a success message like below.

<img width="1432" alt="step 16" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/005bd924-764b-44ca-b48c-499cbf5d5c02">


17. To confirm, scroll up and select monitor, then select view cloudwatch logs

<img width="1432" alt="step 17" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/dc8fe72d-aec2-4b1e-b365-e9602219f121">

18. Click on the most recent event to confirm your Lambda Function has worked. Follow the same steps for LambdaNumberTwo.

<img width="1432" alt="step 18" src="https://github.com/Xalmonte/Invoke-LambdaFunction-with-another-LambdaFunction/assets/169603464/41fc7460-3355-474a-9b4f-5bc95c0d0766">

19. Congratulations! This project was a lot of fun and now we know how to trigger a Lambda Function using another Lambda Function.
