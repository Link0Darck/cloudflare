<h1 align="center">
  <br>
    Cloudflare configuration tutorial for Discord
  <br>
</h1>

You have created a site and you send images or videos but it does not work due to cloudflare and its **Under Attack** mode on Discord!

No problem it's just that it returns a 404 error code (file not found) this is due to cloudflare blocking the **Under Attack** mode and preventing Discord as it sees it as a robot so it sees it as a potential attack but we have the solution to bypass the **Under Attack** mode security only for Discord so follow the tutorial below:

- 1 First step go to cloudflare Dashboard

- 2 Select the site you want to allow Discord to retrieve the images

- 3 Go to the category : **Security**

- 4 Go to the sub-category : **WAF**

- 5 In **Custom rules** click on **Create rule**

- 6 Enter the values on the image or click on **Edit expression** and paste the text from : Expression Preview

**Screenshot :**

<p align="center">
  <img src="https://raw.githubusercontent.com/Link0Darck/cloudflare/main/Img/Value.png"></a>
</p>

**Expression Preview :**

```
(http.user_agent contains "Discordbot/2.0; +https://discordapp.com" and ip.geoip.asnum in {396982}) or (http.user_agent contains "Mozilla/5.0 (Macintosh; Intel Mac OS X 11.6; rv:92.0) Gecko/20100101 Firefox/92.0" and ip.geoip.asnum in {396982}) or (http.request.full_uri contains ":8080" and http.user_agent eq "websocket-sharp/1.0")
```

- 7 Choose the option : **Skip**

- 8 Make your options like the image before saving so as not to be blocked

**Screenshot :**

<p align="center">
  <img src="https://raw.githubusercontent.com/Link0Darck/cloudflare/main/Img/cloudflare2.png"></a>
</p>

- 9 Click on : **Save**

After this you should be able to upload images of your cloudflare protected site to Discord
