# member-list
# 실행화면
![5](https://user-images.githubusercontent.com/104752580/186562440-3cd4c4c6-56ca-4e94-9622-92bbf28d0dbb.JPG)
### 조회 버튼을 누르면 member_list.jsp 파일 페이지로 넘어갑니다.
![10](https://user-images.githubusercontent.com/104752580/186562621-3ec5d454-31f3-4286-8af6-75339eaf9589.JPG)
# 코드 설명
```jsp
<%
	String sql="select custno, custname, phone, address, "
	          +"to_char(joindate,'yyyy-mm-dd') joindate, "
			  +"case when grade = 'A' then 'VIP' when grade = 'B' then '일반' else '직원' end grade, "
			  +"city from member_tbl_02 order by custno asc";

	Connection conn = DBConnect.getConnection();
	PreparedStatement pstmt = conn.prepareStatement(sql);
	ResultSet rs = pstmt.executeQuery();
%>    
```
### to_char를 이용해서 날짜 표시형식을 바꿔준다(ex:20050511->2005-05-11)
### 고객등급을 case when을 이용해서 A는 VIP, B는 일반, 나머지는 직원으로 표시하게 해준다.
### 그리고 마지막에는 도시코드를 불러온다.
### sql변수에서 받아온 쿼리문을 실행하고, 그 실행된 값을 rs에 가져온다.
```jsp
<%
					while(rs.next()) {
				%>
				<tr class="center">
					<td><%= rs.getString("custno")%></td>
					<td><%= rs.getString("custname") %></td>
					<td><%= rs.getString("phone") %></td>
					<td><%= rs.getString("address") %></td>
					<td><%= rs.getString("joindate") %></td>
					<td><%= rs.getString("grade") %></td>
					<td><%= rs.getString("city") %></td>
					<td>
						
						<input type="button" value="수정" >
						<input type="button" value="삭제" ></td>
				</tr>
				<%
					}
				%>
```
### rs에서 가져온 값을 String으로 가져오면서 while문을 통해서 표에 데이터를 넣어주면서 표를 완성시킨다.
