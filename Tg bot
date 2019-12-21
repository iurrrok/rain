from test import uno,get_nearest_value
import time as tt

bot = telebot.TeleBot('')


# Handle all other messages with content_type 'text' (content_types defaults to ['text'])
@bot.message_handler(content_types=['text'])
def echo_message(message):
	dates=[]#даты
	unames=[]#ники
	v1=message.json['from']['username']
	v2=message.date
	if message.text.lower() != '':
		if unames.count(v1) == '':
			unames.append(v1)
			dates.append(v2)
		elif unames.count(v1) == 1:
			k=unames.index(v1)
			dates.remove(dates[k])
			dates.insert(k,v2)
		else:
			print('Error')
	if message.text.lower()== 'ку':
		bot.send_message(message.chat.id, 'ку,ку')
	if message.text.lower() == 'рейн':
		for name in unames:
			bot.send_message(message.chat.id,'Самый активный учатник '+'@'+name)
	if message.text.lower() == 'rain':
		data_inp=1
		hour=message.date-data_inp*3600
		new_date=[]
		for data in dates:
			if data <= hour:
				l=dates.index(data)
				new_date.append(l)
		for i in new_date:
			bot.send_message(message.chat.id,'Aктивные учатники '+'@'+str(unames[i]))
	while True:
		tt.sleep(10)
	#	print(unames,dates)
		print(message.chat.type)
bot.polling()
