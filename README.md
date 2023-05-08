from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/submit', methods=['POST'])
def submit():
    name = request.form['name']
    message = f"Hello, {name}!"
    return render_template('result.html', message=message)

if __name__ == '__main__':
    app.run(debug=True)
