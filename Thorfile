# module: alm

require "thor"

class Alm < Thor
  include Thor::Actions
  require 'alm'
  require 'launchy'
  require 'json'
  require 'pp'

  desc "alm by DOI", "Search for altmetrics by DOI"
  method_option :ids, :default => nil
  method_option :type, :default => nil
  method_option :info, :default => nil
  method_option :source, :default => nil
  method_option :publisher, :default => nil
  method_option :order, :default => nil
  method_option :per_page, :default => nil
  method_option :page, :default => nil
  method_option :instance, :default => nil
  method_option :key, :default => nil
  method_option :options, :default => nil
  def alm(tt)
    tt = "#{tt}"
    say "Searching with doi \'#{tt}\'", :blue
    out = Alm.alm(tt, options)

    #     begin
    #   out = Cites.doi2cit(tt, options[:format], options[:style],
    #                       options[:locale], options[:cache])
    # rescue Exception => e
    #   abort(e.message)
    # end

    say "Found #{out.length} " + (out.length > 1 ? "matches" : "match"), :green
    # for entry in out
    #   if ['citeproc-json'].include? options['format']
    #     pp entry
    #   else
    #     puts entry
    #   end
    # end
  end

end

Alm.start(ARGV)
