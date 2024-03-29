# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: acrooks <acrooks@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2018/11/28 02:40:11 by acrooks           #+#    #+#              #
#    Updated: 2019/06/20 17:45:54 by acrooks          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = libftprintf.a

LISTDIR :=	ft_list/
LIST 	:=	ft_lstadd ft_lstdel ft_lstdelone ft_lstiter ft_lstmap \
			ft_lstnew

MEMDIR	:=	ft_mem/
MEM 	:=	ft_memalloc ft_memccpy ft_memchr ft_memcmp ft_memcpy \
			ft_memdel ft_memmove ft_memset

STRDIR	:=	ft_str/
STR		:=	ft_strcat ft_strchr ft_strclr ft_strcmp ft_strcpy \
			ft_strdel ft_strdup ft_strequ ft_striter ft_striteri \
			ft_strjoin ft_strlcat ft_strlen ft_strmap ft_strmapi \
			ft_strncat ft_strncmp ft_strncpy ft_strnequ ft_strnew \
			ft_strnstr ft_strrchr ft_strsplit ft_strstr ft_strsub \
			ft_strtrim ft_atoi ft_bzero ft_isalnum ft_isalpha ft_isascii \
			ft_isdigit ft_isprint ft_itoa ft_putchar_fd ft_putchar \
			ft_putendl_fd ft_putendl ft_putnbr_fd ft_putnbr ft_putstr_fd \
			ft_putstr ft_tolower ft_toupper ft_cntwrds ft_sqrt \
			ft_close_file ft_read_file ft_abs ft_itoa_base \
			ft_strchr_pos ft_strndup ft_islower ft_isupper ft_putnstr \
			ft_strnchr ft_upper_str get_next_line ft_swap

PFDIR	:=	ft_printf/
PF 		:=	add_flags add_flags2 add_flags3 final_process format_final \
			ft_check_type ft_parsing ft_power_rangers ft_printf \
			prec_float_add prec_float_core prec_float_process \
			result_without_flags type_csp type_dioux type_f

COMPILE :=	gcc -Wall -Wextra -Werror -g -o2
OBJDIR	:=	obj/
SRCDIR 	:=	srcs/
INCDIR	:=	includes/

FILES := $(addprefix $(LISTDIR),$(LIST))
FILES += $(addprefix $(MEMDIR),$(MEM))
FILES += $(addprefix $(STRDIR),$(STR))
FILES += $(addprefix $(PFDIR),$(PF))

SRC := $(addprefix $(SRCDIR),$(addsuffix .c,$(FILES)))
OBJ := $(addprefix $(OBJDIR),$(addsuffix .o,$(FILES)))

all: $(NAME)

$(OBJDIR):
	@echo "Creating library object files directories..."
	@mkdir $(OBJDIR)
	@mkdir $(OBJDIR)$(LISTDIR)
	@mkdir $(OBJDIR)$(MEMDIR)
	@mkdir $(OBJDIR)$(STRDIR)
	@mkdir $(OBJDIR)$(PFDIR)
	@echo "Library object files directory created!"

$(OBJDIR)%.o: $(SRCDIR)%.c | $(OBJDIR)
	@$(COMPILE) -I $(INCDIR) -c $< -o $@

$(NAME): $(OBJ)
	@echo "Compiling library..."
	@ar rc $(NAME) $(OBJ)
	@ranlib $(NAME)
	@echo "Library is compiled!"

clean:
	@echo "Deleting library object files..."
	@rm -rf $(OBJDIR)
	@echo "Library is cleaned!"

fclean: clean
	@echo "Deleting library binary..." 
	@rm -f $(NAME)
	@echo "libftprintf.a is deleted!"

re: fclean
	@$(MAKE) all
