# datenOase-Configs


add these lines for routing configuration (Apache2):
'''
Redirect permanent /PATH/TO/NEXTCLOUD/index.php/apps/dashboard/ https://www.daten-oase.org
Redirect permanent /PATH/TO/NEXTCLOUD/index.php/login?redirect_url=/nextcloud/index.php/apps/files/ https://www.daten-oase.org/

<IF "(%{REMOTE_ADDR} == 'VPN-ADMIN-JUMP-SERVER-IP'  || %{REQUEST_URI} =~ m#/PATH/TO/NEXTCLOUD/index.php/lostpassword/reset/#  ||  %{REQUEST_URI} =~ m#PATH/TO/NEXTCLOUD/index.php/s/# ">

</IF>
<ELSE>
     	Header always unset Cookie
	    Header always  unset Set-Cookie
</ELSE>

'''

add these lines in nextcloud configuration:

´´´
  'remember_login_cookie_lifetime' => 500,
  'session_lifetime' => 500,
  'forcessl' => true,
´´´

