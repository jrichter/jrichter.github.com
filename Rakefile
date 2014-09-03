require 'date'

desc 'create a new draft post'
task :post do
  STDOUT.print "Enter a title: "
  title = STDIN.gets
  title = title.strip

  slug = "#{Date.today}-#{title.downcase.gsub(/[^\w]+/, '-')}"

  STDOUT.print "The filename will be #{slug}.md \n"

  file = File.join(
                   File.dirname(__FILE__),
                   '_posts',
                   slug + '.md'
                   )

  File.open(file, "w") do |f|
    f << <<-EOS.gsub(/^    /, '')
    ---
    layout: post
    title: #{title}
    published: true
    date: #{Time.now}
    ---

    EOS
  end

  system ("#{ENV['EDITOR']} #{file}")
end
