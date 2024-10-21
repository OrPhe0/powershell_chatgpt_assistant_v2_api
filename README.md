# powershell_chatgpt_assistant_v2_api

IMPORTANT: Remember to run function Create-NewThread and reuse that Thread ID so we don't create new Threads each time the script is run. The function is commented out so you can run it isolated

**Script Structure**

**Global Variables**
$apiKey: Your OpenAI API key.
$threadId: The ID of the thread you want to interact with. If not available, run the Create-NewThread function first.
$assistantId: The ID of the assistant that should run on the thread.

**Functions**
Invoke-APIRequest: A utility function to make HTTP requests to the OpenAI API.
Create-NewThread: (Commented out by default) Creates a new thread and returns the thread_id.
Add-MessageToThread: Appends a user message to an existing thread.
Run-ThreadWithAssistant: Runs the assistant on a thread and processes the messages.
Retrieve-ThreadMessages: Retrieves the most recent message from the thread.
Run-Workflow: Orchestrates the steps of adding a message, running the assistant, and retrieving the response.

**Usage**
Reusing Threads:

Run the script once with Create-NewThread to generate a thread, then store the thread_id for future runs.
Example:
powershell
Copy code
$threadId = Create-NewThread
Add a Message to the Thread:

This function appends your message to the specific thread.
Example usage:
powershell
Copy code
Add-MessageToThread -inputMessage "Your query here"
Run the Assistant on the Thread:

Use Run-ThreadWithAssistant to run the assistant on the thread after adding a message.
Example:
powershell
Copy code
Run-ThreadWithAssistant
Retrieve Assistant Responses:

The Retrieve-ThreadMessages function fetches the latest assistant response.
Example:
powershell
Copy code
Retrieve-ThreadMessages
Example Workflow
The following workflow:

Adds a message.
Runs the assistant.
Retrieves the response.
powershell
Copy code
Run-Workflow -input "Please assist me with today's task."
