python
  from telegram.ext import Updater, CommandHandler

  def start(update, context):
      """发送一条消息，当命令 /start 被触发时。"""
      update.message.reply_text('Hello! This is a simple lottery bot.')

  def main():
      """启动机器人。"""
      # 用你的 Bot Token 替换 'YOUR_TOKEN_HERE'
      updater = Updater("YOUR_TOKEN_HERE", use_context=True)

      # 获取 dispatcher 来注册 handlers
      dp = updater.dispatcher

      # 不同的命令 - 回答在 Telegram
      dp.add_handler(CommandHandler("start", start))

      # 开始机器人
      updater.start_polling()

      # 阻塞直到你按 Ctrl-C 或进程收到 SIGINT, SIGTERM 或 SIGABRT。
      updater.idle()

  if __name__ == '__main__':
      main()
  