FROM python:3.9.4

# Create the user that will run the app
RUN adduser --disabled-password --gecos '' ml-api-user

WORKDIR /opt/house-prices-api

#aqui se trata de pasar los argumentos de gemfurry para instalar el modelo empaquetado esta en requirements
# en caso de no querer usar el modelo que se ubica en gemfurry pues habra que añadir el modelo empaquetado  en la carpeta y añadirlo en requirements 
# pip_extra_index_url se declara en la parte de variables de entorno de circleci ver Makefile para entender 

ARG PIP_EXTRA_INDEX_URL

# Install requirements, including from Gemfury
ADD ./house-prices-api /opt/house-prices-api/
RUN pip install --upgrade pip
RUN pip install -r /opt/house-prices-api/requirements.txt

#RUN chmod +x /opt/house-prices-api/run.sh
RUN chown -R ml-api-user:ml-api-user ./

USER ml-api-user

EXPOSE 8001

#CMD ["bash", "./run.sh"]

# otra opcion eliminar el run.sh y poner lo siguiente asi evitamos pasar el port como argumento.

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8001"]
