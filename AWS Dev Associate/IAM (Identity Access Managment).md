for security reasons <font class="highlight-y"> you shouldn't use the ROOT Account.</font> You should create an admin user instead. To better manage user yhou can create groups. Also users can belong to multiple groups.
<font class="h3 highlight-b">IAM Policeis:</font> IAM Policy ingeritance you can assaign policeries tro the group with inheriate that policy. If user bleongs to tow groups they willingerrate both policies. An inline policy is where the policy is only attached to the user. The strucutre of an IAM Policy is a JSON file that consists fo a cersion, ID to identify the policy(optinoal) and a statement. 
The statement consists of
		<li>SID: statment indentifie(optional)</li>
		<li>Effect: this allows or denies access</li>
		<li>Principal: the account/role to the policy will be appplied the actions</li>
		<li>Resources: The resources thats affected by the action</li>
		<li>Condition: detirminds when the policy will take affect(optional)</li>
For IAM password Policy you can set the perameters for the password and if the password can be changed. Multi Factor Authentication is a huge security requirment. They'res hardware keys and virtual key with generating tokens. also have a key fob.
#AWS #AWS-compute #aws-developer-associate