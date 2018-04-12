## Slack API  
  
- https://api.slack.com/  

### Custom Integrations  
  
- https://api.slack.com/custom-integrations  
- Legacy tokens - https://api.slack.com/custom-integrations/legacy-tokens  
  
Legacy token generator에서 토큰을 발급받습니다.  
  
메시징 예제코드
~~~
from slackclient import SlackClient

def slack_message(message, channel):   
    token = ''   
    sc = SlackClient(token)   
    sc.api_call('chat.postMessage', channel=channel, text=message, username='DataLX01', icon_emoji=':robot_face:')
    
slack_message('Server is restarting', '0bigdata_rsch_team')
slack_message('Server is running', '0bigdata_rsch_team')
~~~
