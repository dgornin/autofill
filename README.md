select
	question,
	option_text,
	is_correct,
	count(a.option_id) as number_votes
from
	polls as p
left join polloptions as po
		using(poll_id)
left join answers as a
		using(poll_id,
	option_id)
group by
	question,
	option_text,
	is_correct;
