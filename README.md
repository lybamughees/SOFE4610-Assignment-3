# SOFE4610-Assignment-3  

# Code Explanation
Root:  
Sensor.py - Python code to control the LED and handle the photoresistor input.   
manage.py -  Starting place of Django, used to run the server.  
Light:  
urls.py  - Urls.py is used to control URL patterns, for the application.  
views.py - Initialize the views and view sets used in the application. Handles REST requests and responses to the web interface.  
templates/light/control.html - Used to serve the control page to the user. Buttons post mode(auto/manual) and state(ON/OFF) to control the light.  
serializers.py - Definition of serializers used to return Mode and State objects.  
models.py - Setting up simple models for Mode and State.  
Project:  
urls.py - Urls.py is used to control URL patterns, for the entire project.  
settings.py - Configuration for the Django project.  


# Setup
Before running the code ensure that Django and djangorestframework are installed on your machine.
### Setting up the project:
1. Clone this repository
2. CD into the "project" folder.
3. Run migrations:
```bash
    python3 manage.py makemigrations light
    python3 manage.py migrate
    python3 manage.py createsuperuser
    Username (leave blank to use 'pi'):
    Email address: "leave blank"
    Password: password123
    Password (again): password123
    Superuser created successfully.
```
### Running the Server on the PI

1. To start the server:

    ```bash
    python manage.py runserver 
    ```

2. Open a web browser on the PI and open the following link  
   http://127.0.0.1:8000/   

### Access the web server on an external device  

1. To start the server:

    ```bash
    python manage.py runserver 0.0.0.0:8000
    ```
2. Open a web browser on the external device using the PI IP and open the following link  
   ```
    http://<Pi_IP>:8000
    ```
### Running the Controller Code
1. In another terminal, run the following code 
```sh
python Sensor.py
```
# Using the Program
1. To control the program head to http://127.0.0.1:8000/control  
   NOTE: if you get an error you may need to post the following on the web interface, or ensure that Sensor.py is running.
   * auto to the state list at http://127.0.0.1:8000/mode
   * off to the state list at http://127.0.0.1:8000/state
2. To control the program manually, select the "manual" radio button and select between ON or OFF.
3. To use light detection, select the "auto" radio button and it will turn the light ON/OFF based on the light conditions.

# Application Screenshots


# Demonstration 
