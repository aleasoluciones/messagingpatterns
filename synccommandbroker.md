1 agent at each datacenter to execute commands
The agent can be concurrent or serial
A command broker:
  * dispatch commands for the agents and match the responses
  * it only has one thread and all the operations are sync
  * has a queue/exchange exclusive for the response to it's commands
  * api, pairs of destination agents,commands and the maximun time to get the responses
  * the broker tag the commands with a id and set the reply-to to the queue/excange of the broker and send each command to each agent (in a loop) and start to wait for responses.
  * each agent process the command and send the response with the id to the reply-to queue/exchange
  * the broker get responses until the timeout or the number of valid responses is equal to the number of command sended.
  * the broker discard responses with invalid ids (for example responses from past commands)

 Ex:
  * Get if all of the switches of all datacenters has alarms (using a snmp command).
  * Get on demand info from all datacenters using some kind of db query command.

