# member-list
# 실행화면
![5](https://user-images.githubusercontent.com/104752580/186562440-3cd4c4c6-56ca-4e94-9622-92bbf28d0dbb.JPG)
### 조회 버튼을 누르면 member_list.jsp 파일 페이지로 넘어갑니다.
![10](https://user-images.githubusercontent.com/104752580/186562621-3ec5d454-31f3-4286-8af6-75339eaf9589.JPG)
# 코드 설명
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
