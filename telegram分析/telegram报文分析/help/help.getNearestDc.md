## help.getNearestDc#1fb33026 = NearestDc
### rpc逻辑
返回最近的数据中心
<code>dc := &mtproto.TLNearestDc{Data2: &mtproto.NearestDc_Data{
		Country:   "US",
		ThisDc:    2,
		NearestDc: 2,
	}}</code>