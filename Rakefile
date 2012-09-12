desc 'Help'
task :default do
  puts 'rake preview - Preview the site'
  puts 'rake push - Push to heroku'
end

desc 'Preview the site'
task :preview do
  exec '/Users/makzan/Documents/git_clones/wintersmith/bin/wintersmith preview -p 1234'
end

desc 'Push to heroku'
task :push do
  puts 'Pushing master to heroku'
  exec 'git push heroku master'
end
