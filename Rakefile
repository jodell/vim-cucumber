require 'rake'

VI_DIRS = %w(compiler ftdetect ftplugin indent syntax)

desc 'Install cucumber files to relevant VI folders'
task :install do
  FileList['*'].each do |dir|
    next unless VI_DIRS.include? dir
    FileList["#{dir}/*"].each { |f| 
      puts "Installing #{f} to ~/.vim/#{f}"
      dir = File.expand_path(File.dirname("~/.vim/#{f}"))
      FileUtils.mkdir dir unless File.exist? dir
      FileUtils.cp f, File.expand_path("~/.vim/#{f}")
    }
  end
end
