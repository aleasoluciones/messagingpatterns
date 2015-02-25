1 agent at each datacenter to execute commands
The agent can be concurrent or serial
A command broker (async mode):
  * dispatch commands for the agents and match the responses
  * it only has one thread
  * api, pairs of destination agents and commands and the queue/exchange where the agent should send the replies
  * the broker tag the commands with a id and set the reply-to to the given queue/excange and send each command to each agent (in a loop).
  * each agent process the command and send the response with the id to the reply-to queue/exchange

The responses from the queue/exchange given are processed/consumed by one or more processes completely different to the process that use the command broker to send the command

 Ex:
  * To get all the configuration of all of the network devices, each hour a process send commands to get the configuration and to reply a known queue of configurations.
  * The queue of configurations is consumed by a configurations processes that detect configuration changes and save the change to a persistent store.

