# Business - Panel
# template source
https://github.com/microsoft/python-package-template/tree/main


# just install deps
Installation and Setup
1.Ensure Python and pip are installed.
2.Install project dependencies using:

pip install -r requirements.txt


flit install --only-deps
 

# to publish

Get List of Agents
URL: /
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
page: Page number
size: Page size
filter_params: 
	chat_life_time
	question_count
	search_text
	is_active
Response: Paginated list of agents:
{
  "items": [
    {
      "id": 1,
      "question_count": 0,
      "name": "",
      "chat_life_time": 0,
      "is_active": true
    }
  ],
  "total": 5,
  "page": 1,
  "size": 1
}
Permissions: AGENT_LIST

Find Agent by Details
URL: /find-agent
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
agent_id: ID of the agent
Response: [
  {
    "id": 0,
    "question_count": 0,
    "name": "",
    "chat_life_time": 0,
    "is_active": false,
    "updated_at": null,
    "created_at": null,
    "file_entity": null
  }
]
Permissions: FIND_AGENT

Create New Agent
URL: /create-agent
Method: POST
Headers: Authorization: Bearer <token>
Body:
{
  "name": "agent_name",
  "chat_life_time": 1,
  "question_count": 1,
  "file_ids": []
}
Response: Confirmation of agent creation
Permissions: CREATE_AGENT

Update Agent
URL: /update-agent
Method: POST
Headers: Authorization: Bearer <token>
Body:
{
  "name": "string",
  "chat_life_time": 0,
  "question_count": 0,
  "file_ids": [],
  "id": 0,
  "is_active": false
  
Response: 
{
  "status": 200,
  "message": "عملیات ویرایش رکورد با موفقیت انجام شد"
}
Permissions: UPDATE_AGENT

Deactivate Agent
URL: /deactivate-agent
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
agent_id: ID of the agent
Response: 
{
  "status": 200,
  "message": "غیرفعال سازی با موفقیت انجام شد"
}
Permissions: DEACTIVATE_AGENT

Activate Agent
URL: /activate-agent
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
agent_id: ID of the agent
Response: 
{
  "status": 200,
  "message": "عملیات بازیابی رکورد با موفقیت انجام شد"
}
Permissions: ACTIVATE_AGENT

Delete Agent
URL: /delete-agent
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
agent_id: ID of the agent
Response: 
{
  "status": 200,
  "message": "رکورد با موفقیت حذف شد"
}
Permissions: DELETE_AGENT

Retrieve Agent
URL: /retrieve-agent
Method: GET
Headers: Authorization: Bearer <token>
Query Parameters:
agent_id: ID of the agent
Response: 
{
  "status": 200,
  "message": "عملیات بازیابی رکورد با موفقیت انجام شد"
}
Permissions: RETRIEVE_AGENT
