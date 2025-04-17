# caddybuild
caddy build auto

[caddyserver/caddy](https://github.com/caddyserver/caddy)

```text
export GOOS=linux GOARCH=amd64
xcaddy build v2.8.4 \
              --with github.com/WeidiDeng/caddy-cloudflare-ip \
              --with github.com/mholt/caddy-grpc-web \
              --with github.com/greenpau/caddy-git@v1.0.9 \
              --with github.com/mholt/caddy-webdav \
              --with github.com/WingLim/caddy-webhook@v1.0.8 \
              --with github.com/mholt/caddy-ratelimit \
              --with github.com/caddyserver/ntlm-transport@v0.1.2 \
              --with github.com/lolPants/caddy-requestid@v1.1.2 \
              --with github.com/sjtug/caddy2-filter \
              --with github.com/chukmunnlee/caddy-openapi@v0.11.0 \
              --with github.com/ggicci/caddy-jwt@v0.12.0 \
              --with github.com/caddy-dns/cloudflare \
              --with github.com/libdns/cloudflare@v0.1.2 \
              --with github.com/caddy-dns/route53@v1.5.1 \
              --with github.com/caddy-dns/duckdns@v0.4.0 \
              --with github.com/caddy-dns/dnspod@v0.0.4 \
              --with github.com/caddy-dns/digitalocean \
              --with github.com/caddy-dns/alidns@v1.0.23 \
              --with github.com/caddy-dns/godaddy@v1.0.3 \
              --with github.com/caddy-dns/vultr \
              --with github.com/caddy-dns/googleclouddns@v1.0.4 \
              --with github.com/caddy-dns/ovh@v0.0.3 \
              --with github.com/caddy-dns/metaname@v0.2.0 \
              --with github.com/caddy-dns/ddnss \
              --with github.com/caddy-dns/dinahosting \
              --with github.com/caddy-dns/powerdns@v1.0.1 \
              --with github.com/caddy-dns/tencentcloud@v0.2.1 \
              --with github.com/aksdb/caddy-cgi/v2@v2.2.5 \
              --with github.com/mholt/caddy-l4 \
              --with github.com/caddyserver/replace-response \
              --with github.com/caddyserver/forwardproxy@caddy2=github.com/klzgrad/forwardproxy@naive \
--output ./caddy_linux_amd64
```

Build setp 
```shell

  apt install curl wget vim -y
  
  wget https://golang.org/dl/go1.24.0.linux-amd64.tar.gz
  tar -C /usr/local -xzf go1.24.0.linux-amd64.tar.gz
  export PATH=$PATH:/usr/local/go/bin
  source ~/.bashrc
  go version
  
  
  https://github.com/caddyserver/xcaddy/releases/download/v0.4.4/xcaddy_0.4.4_linux_amd64.deb
  dpkg -i  xcaddy_0.4.4_linux_amd64.deb
  
  
  # query build-info version
  # go list -m -versions github.com/aksdb/caddy-cgi/v2
  
  
  export build_version=v2.8.4
  export build_config=" --with github.com/WeidiDeng/caddy-cloudflare-ip \
  --with github.com/mholt/caddy-grpc-web \
  --with github.com/greenpau/caddy-git@v1.0.9 \
  --with github.com/mholt/caddy-webdav \
  --with github.com/WingLim/caddy-webhook@v1.0.8 \
  --with github.com/mholt/caddy-ratelimit \
  --with github.com/caddyserver/ntlm-transport@v0.1.2 \
  --with github.com/lolPants/caddy-requestid@v1.1.2 \
  --with github.com/sjtug/caddy2-filter \
  --with github.com/chukmunnlee/caddy-openapi@v0.11.0 \
  --with github.com/ggicci/caddy-jwt@v0.12.0 \
  --with github.com/caddy-dns/cloudflare \
  --with github.com/libdns/cloudflare@v0.1.2 \
  --with github.com/caddy-dns/route53@v1.5.1 \
  --with github.com/caddy-dns/duckdns@v0.4.0 \
  --with github.com/caddy-dns/dnspod@v0.0.4 \
  --with github.com/caddy-dns/digitalocean \
  --with github.com/caddy-dns/alidns@v1.0.23 \
  --with github.com/caddy-dns/godaddy@v1.0.3 \
  --with github.com/caddy-dns/vultr \
  --with github.com/caddy-dns/googleclouddns@v1.0.4 \
  --with github.com/caddy-dns/ovh@v0.0.3 \
  --with github.com/caddy-dns/metaname@v0.2.0 \
  --with github.com/caddy-dns/ddnss \
  --with github.com/caddy-dns/dinahosting \
  --with github.com/caddy-dns/powerdns@v1.0.1 \
  --with github.com/caddy-dns/tencentcloud@v0.2.1 \
  --with github.com/aksdb/caddy-cgi/v2@v2.2.5 \
  --with github.com/mholt/caddy-l4 \
  --with github.com/caddyserver/replace-response \
  --with github.com/caddyserver/forwardproxy@caddy2=github.com/klzgrad/forwardproxy@naive  "
  
  # run build
  export GOOS=linux GOARCH=amd64
  xcaddy build $build_version $build_config --output ./caddy_linux_amd64
  
  export GOOS=linux GOARCH=arm64
  xcaddy build $build_version $build_config --output ./caddy_linux_arm64
  
  export GOOS=linux GOARCH=arm;
  xcaddy build $build_version $build_config --output ./caddy_linux_arm
  
  
  export GOOS=android GOARCH=arm
  xcaddy build $build_version $build_config --output ./caddy_android_arm
  
  export GOOS=darwin GOARCH=amd64
  xcaddy build $build_version $build_config --output ./caddy_darwin_amd64
  
  export GOOS=windows GOARCH=amd64
  xcaddy build $build_version $build_config --output ./caddy_windows_amd64.exe
```
