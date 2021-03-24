## Design & implement, Notes Application as a personal productivity tool for quickly taking (& saving) notes, organize notes efficiently. Below are requirments those you need to design.

- Copy 'nodejs-keep-level-4-assignment' and extend it.
- JWT Token module
	- Create a module, which only does JWT token signing and verifying
	- Refer to the methods from this module in `module.js` appropriately
	- You are expected to provide unit tests to this module
	- the signature expected is `signToken(payload, secret, expireIn, callback)` and `verifyToken(token, secret, callback)`
	- Refer these modules appropriately in `module.js`

- Modify existing API **api/v1/users/login**
	- After successful login, response should be look like {token: token, user: {userName: userName, userId: userId}, status: 200}
	- token payload will contain `userName` and 'userId' in the token payload.
	- Token should have expiry time, which is passed while generating the token

- All API for notes
	- All API will be accessible only to authenticated request
	- Only requests with valid token in the Authentication header will succeed, others should get valid HTTP response code and message
	- Write appropriate unit tests to test the authenticated access of the API

- Other instructions
	- Authorization header should be set as Bearer.
	- Use of jsonwebtoken npm module to generate and verify token instead passportjs.
	- If any notes api called without header , it should return 'Not authenticated' message. 
	- Error handling should be done properly in whole application. If any error occurs in Generate and verify token methods, then it should send error message only not whole error object. No need to customize any error message just send as it is.