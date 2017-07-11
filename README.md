# kslab-edx-arsUI
A plugin for edX Analytics Dashboard to represent predicted at-risk students

# engagement_risk.html
at-risk學生燈號網頁架構程式碼放在
/courses/templates/courses/engagement_risk.html

# engagement.py
要在index網頁上加上at-risk學生的tag需在檔案
/courses/views/engagement.py中

在fumction EngagementTemplateView(CourseTemplateWithNavView)中加上新tag的資料
ex:{'name': 'risk', 'label': _('Risk'), 'view':'courses:engagement:risk'},

以及須自行撰寫新的function來將資料傳遞到前端書出
ex:class EngagementRiskStudent(EngagementTemplateView)

# urls.py
要將在engagement.py設定的簡易路徑轉換成實際的url需在檔案
/courses/urls.py

將url的路徑轉換寫入到ENGAGEMENT_URLS = patterns()的list中
ex:url(r'^risk/$', engagement.EngagementRiskStudent.as_view(), name='risk')

