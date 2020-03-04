# Instagram api

## 申請API
https://www.instagram.com/developer/

## get access token
https://www.instagram.com/oauth/authorize/?client_id=xxxxxxxxx&redirect_uri=http://www.xxx.com.tw&response_type=token

## get user info
https://api.instagram.com/v1/users/self/?access_token=xxxxxxxxx

## get location info
https://api.instagram.com/v1/locations/search?lat=24.828034&lng=121.772630&access_token=xxxxxxxx

­­## get location id
https://api.instagram.com/oauth/authorize/?client_id=xxxxxxxx&redirect_uri=http://www.xxx.com.tw&response_type=code&scope=basic+comments+follower_list+likes+relationships+public_content

### PHP
	function api($apiUrl){
		$ch = curl_init();
		curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
		curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
		curl_setopt($ch, CURLOPT_HTTPHEADER, array("Content-type: application/json"));
		curl_setopt($ch, CURLOPT_URL,$apiUrl);
		$result=curl_exec($ch);
		curl_close($ch);
		$_ins = json_decode($result, true);
		return $_ins;
	}
		
	$ins_url = "https://api.instagram.com/v1/users/2008255820/media/recent?client_id=xxxxxxx&count=6&access_token=xxxxxxxxxx";
	$user_url = "https://api.instagram.com/v1/users/self/?access_token=xxxxxxxx";
		
	$_ins = api($ins_url);
	$user = api($user_url);




