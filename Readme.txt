스케쥴 관리 프로젝트

1. 구현기능
	Gantt Chart(일, 주, 월) - 월단위일경우 달력으로 표현 됨
	회원(그룹)
	검색
	채팅 or 덧글

2. 추후 구현
	태그(프로젝트, 작업)
	push server(일정알림 or 덧글알림 등)
	SNS 연동
	디자인 커스터마이징(사용자별 스타일)

3. 작업환경
	안드로이드 스튜디오(Web Service에서 데이터 받은 후 사용자에게 보여주는 역할)
	GitHub(소스 관리)
	몽고DB
	python Flask(Web Service - xml or json) : DB 통신
	
4. DB Layout
	- Member
		MemberKey, ID, PW, NickName, PrimaryKey(email or SNS Key), Group, RegDate, UpdDate
	- Project
		ProjectKey, ProjectName, MemberKey, Auth, RegDate, UpdDate
	- History
		HistoryKey, JobKey, MemberKey, CommentKey, JobHistory
	- Job
		JobKey, JobName, ProjectKey, Step, StartDate, EndDate, MemberKey, 
		Reference(MemberKey), Importance, Progress, RegDate, UpdDate
	- Comment
		CommentKey, JobKey, MemberKey, Comment, RegDate, UpdDate