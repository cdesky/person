# person
个人主页

1、git clone 
2、cnpm install
3、npm run prd (npm run www)
4、pm2 start pm2.json --env uat
  (注:pm2.json  配置对应env_uat里面的后端服务器配置)
   env_uat里面的PORT，需要在nginx代理，指定映射：
   
   eg: http://127.0.0.1:8072/;     127.0.0.1即node服务器IP,8072即node服务器占用端口
   
nginx新增配置（运维）
		location /csp/ {
			proxy_pass http://127.0.0.1:8072/;
			proxy_set_header   Host             $host;
			proxy_set_header   X-Real-IP        $remote_addr;
			proxy_set_header   X-Forwarded-For  $proxy_add_x_forwarded_for;
			proxy_set_header   Cookie $http_cookie;
			proxy_connect_timeout 600;
			proxy_read_timeout 600;
        }
		
5、查看根目录下的目录

  把目录下面的，server目录
				node_modules目录
				pm2.json
				package.json
				压缩成一个压缩包，交给运维。
				
			运维启动服务命令：pm2 start pm2.json --env uat
			
	可能存在的问题，1，部署服务器端口需要开放，
	
	前端检验node服务可用，可以查看logs,(通过统一登录验证)
	
	
