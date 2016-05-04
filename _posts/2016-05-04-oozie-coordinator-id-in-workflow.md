---
layout: post
published: true
title: Getting the Oozie Coordinator ID in a Oozie workflow
comments: true
---

The easiest way is to pass the Coordinator ID in the Coordinator configuration. 


``` xml
<coordinator-app 
	name="demo_coordinator"
	frequency="360"
	start="2100-12-31T23:59Z"
	end="2100-12-31T23:59Z"
	timezone="EST"
	xmlns="uri:oozie:coordinator:0.2"
	>
	<controls>
		<execution>FIFO</execution>
	</controls>
	<action>
		<workflow>
			<app-path>../template/oozie_workflow</app-path>
	        <configuration>
	            <property>
	                <name>COORDINATOR_ID</name>
	                <value>${coord:actionId()}</value>
	            </property>
        	</configuration>
		</workflow>
	</action>
</coordinator-app>
```


<script src="https://gist.github.com/svenhofstede/12fda3b7c94cf74f9c879989cc0f9149.js"></script>


