

pip install uvicorn   
pip install uvloop   
pip install httptools   

sudo a2enmod proxy proxy_ajp proxy_balancer proxy_connect proxy_html proxy_http proxy_wstunnel rewrite ssl   


# Websocket  
ProxyPass /ws/ ws://localhost:8000/ws/  
ProxyPassReverse /ws/ ws://localhost:8000/ws/  

# Http  
ProxyPass /static/ !  
ProxyPass / http://localhost:8000/  
ProxyPassReverse / http://localhost:8000/  


uvicorn settings.asgi:application --reload  
