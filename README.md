[Step 1] first install apps [Step 1]

    apt-get install python3 python3-pip unzip  nginx  gunicorn -y

[Step 2] download scripts

    wget https://github.com/abbasnazari-0/vps_manager/archive/refs/tags/v10.zip &&  unzip v10.zip -d . && mv vps_manager-10/servermanager  /etc/nginx/sites-enabled/servermanager && mkdir servermanager &&  mv vps_manager-10/__init__.py servermanager/__init__.py && rm -rf vps_manager-10 && unlink /etc/nginx/sites-enabled/default &&  nginx -s reload

[Step 3] install python settings

    pip3 install flask  jdatetime jsonpickle

[Step 4] run flask server

    nohup gunicorn -w 3 servermanager:app --bind 0.0.0.0:4000 &
