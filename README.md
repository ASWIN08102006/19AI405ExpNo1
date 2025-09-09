<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Aswin K N</h3>
<h3>Register Number: 212224230027</h3>

<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

<H3>PROGRAM</H3>

```
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.rooms = ["Room1", "Room2"]
        self.patients = {
            "Room1": random.uniform(97.0, 102.0),
            "Room2": random.uniform(97.0, 102.0)
        }
        self.current_room = random.choice(self.rooms)

    def sense(self):
        return self.patients[self.current_room]

    def treat(self, temp):
        if temp > 98.5:
            print(f"Patient in {self.current_room} has fever ({temp:.2f}°F). Prescribing medicine...")
            self.performance += 1
        else:
            print(f"Patient in {self.current_room} is healthy ({temp:.2f}°F). No medicine needed.")

    def move(self):
        next_room = "Room1" if self.current_room == "Room2" else "Room2"
        print(f"Moving from {self.current_room} to {next_room}...")
        self.current_room = next_room
        self.performance -= 1

    def run(self):
        for _ in range(2):
            temp = self.sense()
            self.treat(temp)
            if _ == 0:
                self.move()
        print(f"\nFinal Performance Score: {self.performance}")

agent = MedicinePrescribingAgent()
agent.run()


```
<H3>OUTPUT</H3>

<img width="618" height="97" alt="Screenshot 2025-09-09 133732" src="https://github.com/user-attachments/assets/9c5cfd35-d404-4fc2-bf16-4c1a4d1e5781" />


<H3>RESULT</H3>

<p>Thus the AI agent is developed successfully.</p>

