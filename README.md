<!--
**rlnchow/rlnchow** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
```
from flask import Flask, jsonify

app = Flask(__name__)

def get_life_mantra():
    return "If something is stopping you from doing good, you must change the thing."

@app.route('/funny/<name>')
def funny_response(name):
    if name == "Lakshmi Ravipati":
        return jsonify({
            "name": "Lakshmi Ravipati,\n",
            "message": "The Python loving DevOps Engineer and Automation Enthusiast.\n"
                       "Coach and Coachable, who always cracks the code with a smile.",
            "life_mantra": get_life_mantra()
        })
    else:
        return jsonify({
            "message": f"Sorry, {name} is not as cool as Lakshmi Ravipati.\n"
                       "Try again!",
            "life_mantra": get_life_mantra()
        })

@app.route('/twitter/<handle>')
def twitter_handle(handle):
    if handle == "_ravipati":
        return jsonify({
            "message": "You've found Lakshmi Ravipati's Twitter handle!\n"
                       "Follow for Python, DevOps, and Automation goodness."
        })
    else:
        return jsonify({
            "message": f"Sorry, {handle} is not Lakshmi Ravipati's Twitter handle.\n"
                       "Try again!"
        })

if __name__ == '__main__':
    app.run(debug=True)


```
