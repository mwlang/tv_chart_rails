# TradingView Chart Library Rails Gem
#### version : 1.1.0
#### date : Dec. 26,2014

## Description

This gem provides a simple way to use [TradingView](http://tradingview.com) Chart Library for Ruby on Rails application.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tv_chart_rails', :git => 'git@github.com:bobstar6/tv_chart_rails.git'
```

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install tv_chart_rails

## Usage

1. First of all, ensure your app include jquery.

2. Add `<%= javascript_include_tag 'trading_view_chart' %>` to the template where need to insert tradingview chart.

3. Use `showTradingViewChart()` to initialize a chart.
  
   ```
   <script type="text/javascript">
     showTradingViewChart();
   </script>
   ```
   You can find default params in `tv_chart/vendor/javascripts/trading_view_chart.js`. Initialize your chart by sending hash params to `showTradingViewChart()`. It will overwrite the default params.

4. Put this line to your html page where you want to insert chart.

   `<div id="tv_chart_container"></div>`
   
   You can change the id with hash params.
   
   eg. 

   `showTradingViewChart({ container_id: 'my_own_chart' })`

   then add this line
   
   `<div id="my_own_chart"></div>`

5. If you want to use your own datafeed.js, you can replace it at `tv_chart/vendor/javascritps/charting_library/datafeed/datafeed.js`

## Note

1. when develop your own datafeed, do not use the word 'config' as a method name for route like 'demo_feed.tradingview.com/config', change the word or remap route.

2. if your use the default datafeed.js, you should know this datafeed will use Json.parse to parse the response from ajax request.
