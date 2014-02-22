require "rubygems"
require "rake"

desc "Compile CSS"
task :compile do
    system "sass scss/tempo.scss:tempo.css --style expanded"
    system "sass scss/tempo.scss:tempo.min.css --style compressed"
end # task :compile

