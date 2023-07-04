# Python ChatBot with Tensorflow Serving
### BOT for chat web applications
This project was created as an example of a simple rule base bot for a e-commerce web application

# Requirements 📋
If you have Docker installed in your PC, Docker will install all dependencies and launch the bot service.

# Deploy 🔧⚙️
- After download the repository, execute the notebook "chatbot_dnn_tfx.ipynb" and download the ZIP generated with the Bot in SaveModel tensorflow format.
- Unzip the zip.
- Launch this command:
```
docker run --rm -it -p 8501:8501 -v $(pwd)/chatbot:/models/chatbot -e MODEL_NAME=chatbot -t tensorflow/serving:2.6.0
```
Or just use docker-compose
```
docker-compose build
docker-compose up
```

Once the API is up and runing, you could use the "test.py" file to test the API
Una vez levantado el container puede ensayar la API con el siguiente ejemplo

# Example:
Input:
```
data = {"instances": "Muchas gracias!"}
json_response = requests.post('http://127.0.0.1:8051/predict', data=data)
result = json.loads(json_response.text)['predictions']
print(result)
```

Output:
```
predictions: {
    label: ..., # tipo de respuesta (tag)
    score: ..., # Valor 0 a 1 que indica la precisión de esa respuesta
    messsage: ... # Mensaje del bot como respuesta (texto)
}
```

# Thanks! ✒️
:octocat: Hernán Contigiani 


