# kslab-edx-arsUI
A plugin for edX Analytics Dashboard to represent predicted at-risk students

at-risk學生燈號網頁架構程式碼放在
/courses/templates/courses/engagement_risk.html

要在index網頁上加上at-risk學生的tag需在檔案
/courses/views/engagement.py中

  在fumction EngagementTemplateView(CourseTemplateWithNavView)中加上新tag的資料
  ex:{'name': 'risk', 'label': _('Risk'), 'view':'courses:engagement:risk'},

  以及須自行撰寫新的function來將資料傳遞到前端書出
  ex:class EngagementRiskStudent(EngagementTemplateView)

