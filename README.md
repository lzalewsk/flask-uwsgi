 Builds a base Docker image to run a Flask application using the uWSGI
 application server.
 !!! Requirements for the downstream build !!!

  (1) Declare a CMD instruction to start the uWSGI application server.
      For example:
        CMD ["uwsgi", "--http :5000 --wsgi-file app.py --callable app --processes 2 --threads 4"]

        If running behind a webserver using the uwsgi protocol (like nginx)
        then use `--socket` instead of `--http`.

      For more info, see:
        https://uwsgi-docs.readthedocs.org/en/latest/WSGIquickstart.html
        http://uwsgi-docs.readthedocs.org/en/latest/Nginx.html

  (2) Expose the port uWSGI will run on.
      For example:
        EXPOSE 5000
