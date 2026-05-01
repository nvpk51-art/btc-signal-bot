name: BTC Signal Monitor

  on:
    schedule:
      - cron: '*/30 * * * *'
    workflow_dispatch:

  jobs:
    monitor:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v4
        - uses: actions/setup-python@v5
          with:
            python-version: '3.11'
        - name: Cài thư viện
          run: pip install requests
        - name: Chạy kiểm tra tín hiệu
          env:
            TELEGRAM_TOKEN: ${{ secrets.TELEGRAM_TOKEN }}
            CHAT_ID: ${{ secrets.CHAT_ID }}
          run: python btc_signal.py
