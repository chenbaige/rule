## help.getSupport#9cdf08cd = help.Support
### rpc逻辑
官方解释:`Returns the support user for the ‘ask a question’ feature.`
目前是随意填充的数据
<code>reply := &mtproto.TLHelpSupport{Data2: &mtproto.Help_Support_Data{
		PhoneNumber: "+86 111 1111 1111",
		User:        &mtproto.User{Constructor: mtproto.TLConstructor_CRC32_userEmpty, Data2: &mtproto.User_Data{Id: kSupportUserID}},
	}}</code>