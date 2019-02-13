## help.getTermsOfServiceUpdate#2ca51fd1 = help.TermsOfServiceUpdate
### rpc逻辑
返回1小时后超时
<code>termsOfServiceUpdate := &mtproto.TLHelpTermsOfServiceUpdateEmpty{Data2: &mtproto.Help_TermsOfServiceUpdate_Data{
        Expires: int32(time.Now().Unix() + 3600),
    }}</code>