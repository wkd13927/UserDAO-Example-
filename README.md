# UserDAO-Example-


@DAOClass(id = "basic.UserDAO_TEST", frequency = 1)
public class UserDAO_Test extends AbstractDAO {
	
			//사용자조회
	 		
			public Object selectList(GeneralVO param) throws Exception{
				
						VariableBinder binder = new VariableBinder("basic.user.select.list");
						
						binder.set(" :DEL_YN" , 								param.getString("DEL_YN"));
						binder.set(" :USER_ID" , 								param.getString("USER_ID"));
						binder.set(" :USER_NM" , 							param.getString("USER_NM"));
						
						return this.executeQuery(binder);
						
			}
			
			
	
			
			//팝업조회	
			
			public Object selectDetail(GeneralVO param) throws Exception{
			
						VariableBinder binder = new VariableBinder("basic.user.select.detail");
					
						binder.set(" :DEL_YN",						param.getString("DEL_YN"));
						binder.set(" :USER_CD",						param.getString("USER_CD"));
					
						return this.executeQuery(binder);
					
			
			}
			
			
		
		
			//ID중복체크
		
			public boolean checkDup(GeneralVO param) throws Exception{
			 
			 
						VariableBinder binder = new VariableBinder("basic.user.check.dup");
			 
						binder.set(" :USER_ID",								param.getString("USER_ID"));
			 
						return (((GeneralVOList)this.executeQuery(binder)).size() > 0 );
			 
			 
			}
			
			
			//권한리스트
			
			public Object selectAuth(GeneralVO param) throws Exception {
				
						VariableBinder binder = new VariableBinder("basic.user.select.auth");
						
						return this.executeQuery(binder);
				
			}
			
			
			//Insert
			
			public void insert(GeneralVO param) throws Exception {
				
						VariableBinder binder = new VariableBinder("basic.user.insert");
						
						binder.set(" :USER_ID",                                   	 param.getString("USER_ID"));
						binder.set(" :USER_NM",                                      param.getString("USER_NM"));
						binder.set(" :CLIENT_CD",                                    param.getString("CLIENT_CD"));
						binder.set(" :AUTH_CD",                                       param.getString("AUTH_CD"));
						binder.set(" :USER_PW",                             	         param.getString("USER_PW"));
						binder.set(" :TEL_NO",                                   		 param.getString("TEL_NO"));
						binder.set(" :MOBILE_NO",                                   param.getString("MOBILE_NO"));
						binder.set(" :DEL_YN",                                   		 param.getString("DEL_YN"));
						binder.set(" :POST_NO",                                      param.getString("POST_NO"));
						binder.set(" :ADDR",                               			     param.getString("ADDR"));
						binder.set(" :WORK_IP",                                	     getSession().getWorkIP());
						binder.set(" :INSERT_NO",                                    getSession().getUserCd());
						
						this.executeUpdate(binder);
						
			}
			
		
			
			//업데이트
			
			public void update(GeneralVO param) throws Exception {
				
					VariableBinder binder = new VariableBinder("basic.user.update");
					
					binder.set(" :USER_CD",                                      param.getString("USER_CD"));
					binder.set(" :USER_ID",                                      param.getString("USER_ID"));
					binder.set(" :USER_NM",                                      param.getString("USER_NM"));
					binder.set(" :CLIENT_CD",                                    param.getString("CLIENT_CD"));
					binder.set(" :AUTH_CD",                                      param.getString("AUTH_CD"));
					binder.set(" :USER_PW",                                      param.getString("USER_PW"));
					binder.set(" :TEL_NO",                                       param.getString("TEL_NO"));
					binder.set(" :MOBILE_NO",                                    param.getString("MOBILE_NO"));
					binder.set(" :DEL_YN",                                       param.getString("DEL_YN"));
					binder.set(" :POST_NO",                                      param.getString("POST_NO"));
					binder.set(" :ADDR",                          	             param.getString("ADDR"));
					binder.set(" :WORK_IP",                                      param.getString("WORK_IP"));
					binder.set(" :UPDATE_NO",                                    param.getString("UPDATE_NO"));
				
					this.executeUpdate(binder);
				
			}
			
			
			//삭제
			
			public void delete(GeneralVO param) throws Exception {
				
					VariableBinder binder = new VariableBinder("basic.user.delete");
					
					binder.set(" :USER_CD",                                   param.getString("USER_CD"));
					binder.set(" :WORK_IP",                                   getSession().getWorkIP());
					binder.set(" :UPDATE",                                    getSession().getUserCd());
					
					this.executeUpdate(binder);
			}
			
			
}
