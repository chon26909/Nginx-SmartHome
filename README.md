# Nginx-SmartHome

server 
{
        listen 80;
        server_name mqtt.chon.host;

        location / {
                proxy_pass http://127.0.0.1:1883;
                proxy_http_version 1.1;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $host;
                proxy_cache_bypass $http_upgrade;
        }
}


#
