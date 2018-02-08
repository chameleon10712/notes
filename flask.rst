================================
			Flask
================================

Unique URLs / Redirection Behavior
	<http://flask.pocoo.org/docs/0.12/quickstart/>
	
	trailing slash
		localhost:5000/projects   -> 無 trailing slash
		locaohost:5000/projects/  -> 有 trailing slash
		
	Flask Unique URLs / Redirection Behavior::
		@app.route('/projects/')
		def projects():
			return 'The project page'

		@app.route('/about')
		def about():
			return 'The about page'	

	如果用 '/projects/' 的寫法
		網址輸入 localhost:5000/projects 的話會自動導向 localhost:5000/projects/
		網址輸入 localhost:5000/projects/ 也會正常顯示

	如果用 '/about'     的寫法
		網址輸入  localhost:5000/about  會正常顯示
		網址輸入  localhost:5000/about/ 會顯示 404 Not Found

URL Building
	<http://flask.pocoo.org/docs/0.12/quickstart/>


Context Locals
	http://flask.pocoo.org/docs/0.12/quickstart/#context-locals


flask + sqlalchemy login example
	https://github.com/tolgahanuzun/Flask-Login-Example

Flask: 'session' vs. 'g'?
	https://stackoverflow.com/questions/32909851/flask-session-vs-g

When should Flask.g be used?
	https://stackoverflow.com/questions/15083967/when-should-flask-g-be-used

Flask sessions, where are the cookies stored?
	https://stackoverflow.com/questions/37068604/flask-sessions-where-are-the-cookies-stored


Building a Bootstrap table with dynamic elements in Flask
	https://stackoverflow.com/questions/32774118/building-a-bootstrap-table-with-dynamic-elements-in-flask






