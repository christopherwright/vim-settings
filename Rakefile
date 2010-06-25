vimdir = File.expand_path("~/.vim")
vimrc  = File.expand_path("~/.vimrc")

desc "Install vim configuration"
task :install do
  puts "Installing to #{vimdir}"
  sh "mkdir -p #{vimdir}" unless FileTest.directory?("#{vimdir}")
  sh "tar -cpf - * | (cd #{vimdir} && tar -xpf -)"
  puts "Creating link for #{vimrc}"
  File.symlink("#{vimdir}/vimrc", vimrc) unless File.exists?(vimrc)
end

task :default => :install
